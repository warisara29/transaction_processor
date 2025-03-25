class TransactionProcessor:
    def __init__(self):
        self.balance = 0  # Internal balance
        self.log = []  # Stores transaction logs

    def process_transaction(self, transaction):
        """Processes a single transaction."""
        trans_id = transaction["id"]
        trans_type = transaction["type"]
        amount = transaction["amount"]

        if trans_type == "deposit":
            self.balance += amount
            self.log.append(f"Transaction {trans_id}: Success - Deposited {amount}")

        elif trans_type == "withdrawal":
            if self.balance >= amount:
                self.balance -= amount
                self.log.append(f"Transaction {trans_id}: Success - Withdrew {amount}")
            else:
                self.log.append(f"Transaction {trans_id}: Failed - Insufficient balance")

    def process_transactions(self, transactions):
        """Processes a list of transactions in order."""
        for transaction in transactions:
            self.process_transaction(transaction)

    def get_log(self):
        """Returns the transaction log as a list of strings."""
        return self.log


# Sample transactions
transactions = [
    {"id": 1, "type": "deposit", "amount": 200},
    {"id": 2, "type": "withdrawal", "amount": 50},
    {"id": 3, "type": "deposit", "amount": 100},
    {"id": 4, "type": "withdrawal", "amount": 500}  # Should fail due to insufficient balance
]

# Run the processor
processor = TransactionProcessor()
processor.process_transactions(transactions)

# Print logs
for entry in processor.get_log():
    print(entry)
