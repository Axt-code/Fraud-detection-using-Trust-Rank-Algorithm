# TrustRank Algorithm for Identifying Bad Senders
## Overview
This project applies the TrustRank algorithm, originally designed to combat web spam, to detect bad senders in a financial transaction network. By assigning fraud scores to known bad senders and iteratively propagating these scores through a graph of transactions, we can identify potential fraudulent senders.

## Files
Payments.csv: Contains transactions with columns for sender, receiver, and transaction amount.
bad_senders.csv: Contains a list of known bad senders.
How It Works
## Graph Construction:

The Payments.csv file is read, and a directed graph is built where senders and receivers are nodes, and transactions are edges. Each transaction's amount serves as the edge weight.
TrustRank Algorithm:

Known bad senders (from bad_senders.csv) are used as the seed set and are assigned an initial fraud score.
The fraud scores are iteratively propagated through the graph, where the score of a node increases based on its connection to other bad senders.
Fraud Score Calculation:

Transaction weights are normalized for each sender.
Scores are propagated through the network and adjusted using a constant factor (α) until convergence is reached.
The final fraud scores are used to update the list of bad senders, identifying potential fraudulent actors.

## How to Run the Project

Install Dependencies:

Python 3.x
pandas, networkx, matplotlib
To install the necessary packages, run:

`pip install pandas networkx matplotlib`

## Steps:

Clone or download the project.
Place Payments.csv and bad_senders.csv in the project directory.
Run the Python script to execute the TrustRank algorithm and identify potential bad senders.
Visualization:

After execution, the script will generate a plot showing the distribution of fraud scores across senders, highlighting both known and newly identified bad senders.

## Output
A list of potential bad senders is updated based on the fraud scores.
Convergence information and fraud score plots are generated for further analysis.
