## ASSIGNMENT
### Spot the invariants (system and function)

#### System
- The sum of all users' balances (balances) should equal totalDeposited
- totalDeposited should never exceed MAX_DEPOSIT_AMOUNT (1,000,000 tokens).
- The token balance of the contract should equal the totalDeposited plus any unpaid interest that has been accrued but not yet distributed.
- If a user has made a deposit, their timestamps[user] should be greater than 0.
- No user's balance in the balances mapping should ever become negative.
- totalDeposited should never be negative

#### Functional
- For the deposit(uint256 amount)
  - The amount must be greater than or equal to MIN_DEPOSIT_AMOUNT (1 token)
  - The user's balance must increase by exactly amount.
  - totalDeposited must increase by exactly amount.
  - The contract must receive amount tokens from the user via token.transferFrom(msg.sender, address(this), amount).
  - timestamps[msg.sender] must be set to the current timestamp if it is not already set (i.e., the user's first deposit).

- For withdraw(uint256 amount, address _addr)
  - The user must have sufficient balance to withdraw the specified amount
  - The user's balance must decrease by exactly amount.
  - totalDeposited must decrease by exactly amount.
  - The specified _addr must receive amount tokens via token.transfer(_addr, amount).

- For getInterestPerAnnum()
  - The user must have waited at least one year since their last deposit
  - The user must have a positive balance to earn interest.
  - The contract's token balance must reduce by the calculated interest, and the user's token balance must increase by the same amount.

