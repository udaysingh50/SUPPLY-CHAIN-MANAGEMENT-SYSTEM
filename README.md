# Supply Chain Management System with Blockchain
Overview
This project is a Supply Chain Management System built using blockchain technology to address distribution challenges faced by a manufacturing company. The system ensures the secure and transparent movement of products from the manufacturer to clients through distributors while resolving common distribution issues.

Features
Participant Registration: Manufacturers, distributors, and clients can register in the system.
Clients and distributors deposit a security amount with a trusted third party.

Blockchain Security: Implements a Proof of Work (PoW) consensus algorithm for blockchain security.

Merkle Tree Implementation: Calculates the hash of all transactions in a block using a Merkle tree.

Product Status Tracking: Generates QR codes to view the current product status in the supply chain.

Sequential Product Distribution: Ensures that only one product distribution can occur at a time. Requires confirmation from both distributor and client for the next delivery.

Issue Resolution: Identifies and resolves well-known issues:
a. Distributor dispatched, client received, but client denies (lying client).
b. Distributor did not dispatch, client did not receive (lying distributor).
Deducts from the security deposit of the dishonest party.

Prerequisites
Python 3.x

Usage: run "python blockchain.py" in terminal
Then type the following numbers for the specific commands
1. Register Manufacturer
2. Register Distributor
3. Register Client
4. Client requests for product
5. Distributor receives the product from the manufacturer
6. Distributor dispatches the product
7. Client receives the product
8. Predict and Log Issues
9. Generate QR Code
10. Exit

Register Participants:
Run the program and follow the prompts to register manufacturers, distributors, and clients.
Distribute Products:

Distributors can distribute products to clients by providing necessary details.
Both distributor and client must confirm the transaction.
Resolve Issues:

Use the "Predict and Log Issues" feature to identify and resolve distribution issues.
Deductions from the security deposit are automated based on issue resolution.
Generate QR Codes:

QR codes can be generated to view the current product status in the supply chain.

About code:
Class Participants
The Participants class represents the entities involved in the supply chain system, including manufacturers, distributors, and clients. Each participant has attributes such as name, security_deposit, and flags indicating their role in the system (is_client, is_manufacturer, is_distributor). This class is responsible for registering and managing participants.

Attributes:
name: Name of the participant.
security_deposit: The amount deposited as a security measure.
is_registered: A flag indicating if the participant is registered.
is_client: A flag indicating if the participant is a client.
is_manufacturer: A flag indicating if the participant is a manufacturer.
is_distributor: A flag indicating if the participant is a distributor.
is_distributing: A flag indicating if a distributor is currently distributing a product.

Class Transactions
The Transactions class represents the basic structure of a transaction in the supply chain. Each transaction records the flow of a product from the manufacturer to a distributor and then to a client, along with timestamps at key stages.

Attributes:
ID: A unique identifier for the transaction.
Client_id: ID or name of the client involved in the transaction.
Distributor_id: ID or name of the distributor involved in the transaction.
Product_id: ID or name of the product being distributed.
Timestamp_1: Timestamp when the distributor receives the product from the manufacturer.
Timestamp_2: Timestamp when the distributor dispatches the product to the client.
Timestamp_3: Timestamp when the client receives the product.

Class Block
The Block class represents a block in the blockchain. Each block contains a set of transactions, and it includes attributes such as index, previous_hash, timestamp, and a nonce. Additionally, it calculates the Merkle root and hash of all the data within the block.

Attributes:
index: The index or position of the block in the blockchain.
previous_hash: The hash of the previous block in the blockchain.
timestamp: The timestamp indicating when the block was created.
transactions: The list of transactions included in the block.
nonce: A value used in the proof-of-work (PoW) algorithm to find a valid block hash.
merkle_root: The root hash of the Merkle tree of transactions in the block.
hash: The hash of the entire block, including all its attributes.

Class Blockchain
The Blockchain class manages the blockchain itself and the overall supply chain system. It includes functions for creating blocks, adding blocks to the chain, conducting proof-of-work, registering participants, distributing products, confirming receipts, resolving issues, generating QR codes, and more.

Attributes:
chain: A list representing the blockchain, starting with the genesis block.
participants: A dictionary containing registered participants.
difficulty: The difficulty level of the PoW algorithm.
product_status: A dictionary tracking the status of products being distributed.
issue_log: A list for logging distribution and receipt issues.
count_manufacturer: A count of registered manufacturers.
The Blockchain class also includes functions to register participants, distribute products, confirm receipts, predict and log issues, and generate QR codes, among others.
