# Solana-Recipe
## Under/Over flow 
https://www.sec3.dev/blog/understanding-arithmetic-overflow-underflows-in-rust-and-solana-smart-contracts
## Never Use Floats for Money
https://husobee.github.io/money/float/2016/09/23/never-use-floats-for-currency.html
## Anchor size
https://www.sec3.dev/blog/all-about-anchor-account-size

## ATA in contract 
	#[derive(Accounts)]
	pub struct Initialize<'info> {
 	#[account(
        init_if_needed,
        payer = payer,
        associated_token::mint = mint,
        associated_token::authority = payer
    )]
    pub token_account: Account<'info, TokenAccount>,
    pub mint: Account<'info, Mint>,
     #[account(mut)]
    pub payer: Signer<'info>,
    pub system_program: Program<'info, System>,
    pub token_program: Program<'info, Token>,
    pub associated_token_program: Program<'info, AssociatedToken>,
    pub rent: Sysvar<'info, Rent>,
	}


https://www.soldev.app/course/anchor-pdas


# SPL Token Extension
## Mint Close Authority 
will close the token mint account 


Remove token,treat as vaccant address


Only valid if supply is 0 


spl-token --program-id TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb close-mint <Mint Address>
