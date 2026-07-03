package qn2_Exceptions;

// Setting up a custom checked exception
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

// A simple account class to show how we can conditionally throw it
class BankAccount {
    private double balance = 50000.0;

    public void withdraw(double amount) throws InsufficientFundsException {
        System.out.println("Processing withdrawal request for: UGX " + amount);
        
        if (amount > balance) {
            throw new InsufficientFundsException("Transaction Denied: Withdrawal amount exceeds available balance.");
        }
        
        balance -= amount;
        System.out.println("Withdrawal successful. Current balance: UGX " + balance);
    }
}
