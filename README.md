# Technical Analysis of Solana

[Solana](https://www.solana.com) is a blockchain platform
that claims to offer fast transaction settlement at a low cost.

While a substantial amount of money has already been invested and "locked" in the platform,
there is, shockingly, no technical analysis of its [key concepts and components](https://medium.com/solana-labs/7-innovations-that-make-solana-the-first-web-scale-blockchain-ddc50b1defda), neither from the Solana team itself nor from external parties.

A high-level analysis based on available documentation alone reveals several shortcomings including:

* **Lack of technical analysis**: Solana employs non-standard techniques yet does not provide any technical analysis. It is unclear under what assumptions regarding the networking model or node failure model the system can guarantee any service to work reliably.
* **Inconsistent documentation**: There are many inconsistencies between the white paper, blog posts, and technical documents on their website, making it hard to derive a coherent view on their system, which prevents independent parties from conducting their own analyses.
* **Dubious technical contributions**: From the available documentation, it does not become clear whether there is any merit to their technical solutions. Their "proof of history" mechanism introduces a hash-based source of time, which is inefficient and does not solve any concrete problem. It is intended to reduce the message complexity in BFT algorithms but is not shown to have that effect. Similarly, their "Tower BFT" algorithm is not shown to have the required agreement and liveness properties.
* **Low efficiency**: Given the need to continuously produce hashes at a high rate, it is an inefficient mechanism to order transactions, requiring significantly more computational cycles than any proof-of-stake protocol.
Moreover, the short block time results in many discarded forks, further reducing the efficiency of the system.
* **Significant hurdles to decentralization**: Given that the validators pay for their own vote transactions, a substantial stake is required for voting rewards to exceed the voting fees, which bars interested parties from becoming validators.

Given that a lot of documentation is vague and outdated, a thorough analysis requires examining the source code itself.

This repository is meant as a collection of technical analyses with the goal of deriving the conditions required for the platform to work. A secondary goal is to determine Solana's computational and message complexity.

Potential users, investors, and developers in the Web3 space can then use the findings compiled here to learn about the technical properties of Solana and help them to decide whether it is the right platform for their purpose.
