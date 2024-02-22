<details>

<summary><b>My section header in bold</b></summary>

<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-AMS_HTML"></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
    });
</script>

</details>

# FreeWillAI: Decentralized Machine Learning Inference on Blockchain Networks

## Abstract

FreeWillAI introduces a revolutionary approach to AI by integrating it with blockchain technology, offering a decentralized, uncensored, and secure platform for AI model execution. By leveraging the transparency, immutability, and auditability of blockchain networks, FreeWillAI addresses critical issues in current AI systems such as centralization, censorship, data privacy, and the lack of incentives for community contributions. The solution encompasses a user-friendly API for uploading AI models and conducting inferences, supported by a smart contract framework to ensure secure data handling and consensus-based validation of AI inferences. This abstract encapsulates the vision for a more collaborative, transparent, and secure AI development ecosystem.

## Introduction - Description of the problem

Running AI models on blockchain networks is essential for several compelling reasons. Imagine blockchains as data repositories that offer not only answers but also a clear record of inputs and outputs. They provide transparency, immutability, uncensorship and an audit trail—qualities that current AI systems often lack. Here's why it matters:

- *Decentralization*: By spreading the AI model training process across multiple nodes in a blockchain network, we reduce reliance on centralized platforms. This can lead to fewer data breaches, less downtime, and enhanced security.

- *Uncensorship*: as the network running the AI models is no longer controlled by a single entity, there is no possibility to censor or regulate the content and data. As history has already showed, for example, with the [block of Wikipedia in Turkey](<https://en.wikipedia.org/wiki/Block_of_Wikipedia_in_Turkey>), blockchain running systems can be an extremely [safe and efficient solution to avoid censorship](<https://observer.com/2017/05/turkey-wikipedia-ipfs/>).

- *Data Privacy*: Blockchains use clever cryptographic techniques to store and process data. This boosts data privacy, helping to address concerns about data confidentiality and consent in AI development.

- *Incentives*: Blockchain-based AI training platforms can use cryptocurrencies or tokens to encourage users to contribute computational resources or share their data for model training. This fosters a more collaborative and inclusive AI development community. Besides, relying on the project’s solid infrastructure, FWAI’s token manages to achieve an elevated initial intrinsic value.

By harnessing the power of decentralized blockchain systems, we create a more secure, transparent, and collaborative environment for AI training. This approach lets AI developers tap into the vast computational resources of blockchain networks while addressing data privacy and security concerns associated with centralized platforms.

Furthermore, blockchain's digital record helps explain AI's inner workings and the source of its data, a significant step towards more understandable AI. It enhances trust in data integrity, which in turn boosts confidence in AI recommendations. Storing and sharing AI models on the blockchain adds an audit trail, enhancing data security—a win-win for the future of AI and data management.

## Solution overview

### General protocol

FreeWillAI addresses a fundamental need: the ability to conduct decentralized AI inferences on the blockchain, free from regulation or censorship. Our system offers a blockchain network where clients, such as enterprises, can effortlessly upload their AI models via a user-friendly API. Subsequently, users, typically employees of the enterprise, can supply test data to execute inferences using the uploaded model. This entire process is accessible through the API, sparing users from the intricacies of backend operations.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.001.png" alt="Simplified" width="400" height="auto">

Within FWAI's network, the process relies on the FWAI [Smart Contract](<https://en.wikipedia.org/wiki/Smart_contract>).

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.002.png" width="400" height="auto">

After executing the model, each node transmits the inferences (the results obtained from running the AI model with the provided data) back to the FWAI Smart Contract. This contract then submits the responses to a consensus mechanism to determine which answer is considered correct before sending it to the user.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.003.png" width="400" height="auto">

The consensus mechanism is based on a majority threshold: if the number of identical answers surpasses this threshold, that answer will be deemed correct by the Smart Contract. The standard threshold is 50%: the answer with the majority support is considered correct. However, for more rigorous results, the threshold can be increased.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.004.png" width="400" height="auto">

### Border case: unresolved consensus 

If a majority consensus is not reached, there are several strategies to address the situation. 
The first and most straightforward approach is to refund the stakes to the participating nodes and return the running tokens to the client, indicating that consensus was not achieved. 
Another option is to repeat the task until the consensus threshold is met. 
During each attempt where consensus is not reached, the responses from the nodes are recorded to maintain a history of answers. 
After sufficient iterations result in consensus, the final responses from the nodes are compared to their previous submissions stored in the record. 
Nodes that consistently provided incorrect answers are penalized by forfeiting their stake.

## Future improvements

We proceed to explain the idea of a future improvement designed to reduce the gas cost of running tasks without sacrificing the network’s security robustness, which includes the well known proof-of-stake (PoS) protocol.

### Staking System

In the future network, which will utilize a proof-of-stake (PoS) protocol, there is a staking system. This system serves as a means of allocating tasks based on the stake of participants, contrasting with the computational power-based approach typical of proof-of-work (PoW) protocols. The staking system operates as follows:

1. *Stake Commitment:* After enlisting as validators, the nodes commit a specified amount of stake in the form of the network's tokens, FWAI. This stake signifies their dedication to the network and their ability to run AI models.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.005.png" width="400" height="auto">

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.006.png" width="400" height="auto">


2. *Selection for AI Model Execution*: Based on their staked amount, nodes are selected by FWAI’s Smart Contract to execute specific AI models or tasks. Nodes with higher stakes are more likely to be chosen, reflecting their greater resources or stronger commitment to the network.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.007.png" width="400" height="auto">

3. *Execution of AI Models*: Upon selection, a node executes the AI model according to the request. The Smart Contract defines the execution rules and parameters, ensuring that the node adheres to the established framework.

4. *Rewards and Penalties*: Successful completion of AI model execution results in rewards for the node, typically in the form of additional FWAI tokens. In contrast, failure to accurately execute the model or engaging in malicious activities can lead to penalties, such as a reduction in their staked tokens.

5. *Network Integrity and Efficiency*: The PoS mechanism ensures that nodes with larger stakes, which presumably have better resources, are more frequently chosen to run complex AI models. This approach enhances both the efficiency and reliability of AI computations on the network. Moreover, the potential penalties for subpar performance or dishonesty incentivize nodes to maintain high operational standards.

### Random Audits

To ensure the integrity of the network and prevent the influence of malicious nodes, the Smart Contract incorporates a feature for random audits of the results provided by the node selected through the PoS system.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.008.png" width="400" height="auto">

If a node is not chosen for an audit, the process continues as usual: the network rewards the node for executing the AI model and forwards the results to the user.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.009.png" width="400" height="auto">

Conversely, if a node undergoes an audit, the Smart Contract then requests verification from all other participating nodes to cross-check the results initially provided by the selected node.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.010.png" width="400" height="auto">

The Smart Contract compares these responses and bases its decision on the consensus among the participating nodes. Depending on whether the majority corroborates the initial result, the Smart Contract will either reward or penalize the node initially chosen.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.011.png" width="400" height="auto">

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.012.png" width="400" height="auto">

### Security Levels

Since every data transaction between nodes and the Smart Contract incurs a 'gas' fee, 
payable in $ETH$ tokens due to the operation of the Smart Contract on the Ethereum Network, we've developed a process that aims to reduce the total 'gas' cost. 
To achieve this, users sending test data must also submit a security level number. 
This number dictates the likelihood of the executing node being audited, with 1 representing the highest level, meaning the node is certain to be audited with odds of $\frac{1}{1}$. 
The default value is set at $1000$, indicating that audits will occur with odds of $\frac{1}{1000}$. 
In practice, this means for every $1000$ tasks executed, at least one will undergo an audit.

Generally, for a client sending a task with a security level number $S$, the probability of that task being audited is $\frac{1}{S}$.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.013.png" width="400" height="auto">

Once the user has set the security level, the Smart Contract randomly determines whether to audit the selected node, taking into account the security level specified by the user.

<p align="center">
    <img src="whitepaper_imgs/Aspose.Words.59132ecd-8524-44cb-8d30-8fe65f8ab187.014.png" width="400" height="auto">

We must now calculate the punishment payment to ensure that replicating incorrect answers is not profitable. The required staking amount should be a minimum stake, *M*, plus the reward *R* for executing each task, multiplied by *S*, the security level, to ensure that the loss from being audited outweighs the earnings from running *S* tasks.

For instance, with a security level of $1000$, a node will be audited once for every $1000$ rewards earned. If a node has accumulated $1000 \; \text{FWAI}$ in rewards from tasks that were not audited, the potential loss when audited should exceed $1000 \; \text{FWAI}$ to administer an effective punishment.

This mechanism guarantees that providing incorrect results to gain rewards is never profitable. To incur a loss greater than $1000 \; \text{FWAI}$, a node must have staked that amount. Therefore, the staking amount could be equivalent to the reward for each task execution multiplied by the security level. However, with such a staking requirement, providing incorrect results could still appear "profitable" to a malicious node. This is because a malicious node could execute $1000$ tasks with incorrect results, earning $1 \; \text{FWAI}$ per execution for a total of $1000 \; \text{FWAI}$. If one of these tasks is audited, the punishment would equal the staked amount, which is $1000 \; \text{FWAI}$ in this scenario ($1 \; \text{FWAI of reward} \times 1000 \; \text{security level}$), leading to a net balance of $0$ and no financial loss for the malicious node. Based on this logic, we establish a minimum stake of $10 \; \text{FWAI}$ to ensure an effective deterrent against providing incorrect results.
 Staking is required for every task executed.


### Staking requirements

> $\text{Staking amount} = \underbrace{10 \, \text{FWAI}}_{\text{minimum stake}} + \underbrace{1 \, \text{FWAI}}_{\text{reward}} \times \text{Security level}$

**For security level of 1000:**

> $\text{Staking amount} = 10 \, \text{FWAI} + 1000 \, \text{FWAI} = 1010 \, \text{FWAI}$

\
Formalizing the previous reasoning, we have:

> The probability of an audit taking place for a given task run is $\frac{1}{S}$

> Therefore, the expected number of audits after $n$ task runs is $\frac{n}{S}$

> Meanwhile, the staking amount $A$ is given by the formula:

$$A= m+R \, \times \, S$$

> Where $m$ is the *minimum stake*, $R$ is the *reward* for running a task and $S$ is the *security level* 

> Now, let's consider the total earnings and stakes after $n$ task runs. The total earnings $E$ is the sum of rewards for each task run:

$$E=\sum_{i=1}^{n}{R}$$

> The total stakes $T$ is the sum of the staking amount for each audit:

$$T=\sum_{i=1}^{n}{A}$$
$$= \sum_{i=1}^{\lfloor{\frac{n}{S}}\rfloor}{m+R \, \times \, S}$$
$$=\lfloor{\frac{n}{S}}\rfloor \, \times (m+R \, \times \, S)$$

> Here, $\lfloor{\frac{n}{S}}\rfloor$ represents the number of audits that have taken place after $n$ task runs.

> For the system to administer an appropriate punishment, the total stakes should be greater than the total earnings:

$$T > E$$
$$\lfloor{\frac{n}{S}}\rfloor \, \times (m+R \, \times \, S) > \sum_{i=1}^{n}{R}$$
$$\lfloor{\frac{n}{S}}\rfloor \, \times (m+R \, \times \, S) > n \times R$$

<br/><br/>

## Technical details

To be developed.


## Mathematical formalization of the Smart Contract

We define the set of network nodes as $N$, and the answer returned by a node $n$ as a function from the set of nodes $N$ to the set of answers $A$, denoted by $f: N\rightarrow A$.
Therefore, given a node $n$, we have:
$$f(n)= \text{answer returned by the node }n$$

In the basic majority consensus system, the Smart Contract operates as follows:

* It identifies the majority answer by:
$$maj=\underset{a \, \in A}{\mathrm{arg max}}\{ \sum_{n \in N}{\mathbb{1}_{A_{a}}(n)}\}$$
where 
$$A_{a}=\{ n \in N:f(n)=a\}$$

* Therefore, the set of nodes that have voted for the majority answer is defined as:
$$M=\{ n \in N: f(n)=maj\}$$

* Supposing that all the nodes in the network have staked (or just taking $N_S$ as the set of nodes participating of the stake), and given a threshold $t$ to 
determine majority (the predetermined value is $t=50\%$),  
