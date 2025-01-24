System-Level Invariants
    1. totalDeposited Cannot Exceed MAX_DEPOSIT_AMOUNT
    2. The Total Deposited Is Equal to the Sum of All User Balances
    3. User Balances Cannot Be Negative
    4.  Deposit Amount Cannot Exceed MAX_DEPOSIT_AMOUNT
    5.  Deposit Amount Must Be At Least MIN_DEPOSIT_AMOUNT

Function-Level Invariants
    1. User Cannot Withdraw More Than Their Balance
    2. User Balance Is Correctly Updated
    3. Interest Can Only Be Claimed After One Year
    4. User Must Have Made a Deposit to Get Interest
    5. totalDeposited Should Be Correctly Updated After a Withdrawal