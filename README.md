# Message-based-communication

JAVA; JMS; JPA; EJB; XML; XSD.

Scenarion that makes use of messaging to support interaction between a Store, Store users and a Bank.
All communication between the three nodes is supported with JMS.

# User:
• List all books in the store (the information is provided by the store).
• List all books matching a certain title.
• Make a purchase order for one book, for which the user contacts the store with all necessary information, including (fictitious) credit card details.
• See previously purchased books.
• See pending purchases.
• See current credit (a fictitious credit card number is sent to the bank).
• Make a bank deposit (using a fictitious credit card number as the deposit target).

# Store 
• Receive a purchase order for a book, acknowledge the reception, and forward the
information to the bank. When the bank replies with a positive answer the store
admin is notified and is able to go through all pending orders and prepare the
corresponding book for shipping (as packaging and shipping is a manual step we
simulate these activities by interacting with the console and marking a pending
order as concluded). This will result in registering the conclusion of the purchase
order in the database and notifying the order owner. If the bank response is negative,
notify the order owner.
• View pending orders.
• Announce a new book is available for purchase. No store users can afford to lose this
information.

# Bank
• Receive purchase information and automatically approve the payment if the user
credit stands. Otherwise, the payment should be set to pending (to try later). In both
cases notify the sender.
• View pending payments and be able to manually approve those for which the client
has credit.
• View approved and rejected payments.
