# Othentic

Othentic Stack is AVS development framework. 

For more details, check the Official Documentation here: - https://docs.othentic.xyz/main

# Network Management
Please check out the [src/NetworkManagement](https://github.com/Othentic-Labs/core-contracts/tree/main/src/NetworkManagement) folder to learn about the AVS contracts.

![image (12)](https://othentic.gitbook.io/~gitbook/image?url=https%3A%2F%2F740349061-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FOU9BNZyLM0Zg4ujkq3Zn%252Fuploads%252FZVjdrZiFWxuhgLyXYv7c%252FAbstract---high-level%2520%282%29.png%3Falt%3Dmedia%26token%3D7386b3f5-abe6-4432-ad20-0c3b235dee04&width=768&dpr=4&quality=100&sign=e90c2bc7&sv=1)

Each validator holds a private key linked to their restaked and delegated stake tokens, granting them voting power and also exposing them to slashing and penalties for malicious behavior. In the Othentic Stack, developers focus on the logic of [Tasks](https://docs.othentic.xyz/main/avs-framework/othentic-consensus/task-and-task-definitions#task) execution and validation. Performers execute the tasks, while attesters vote on the quality of the work.

Network governance is managed by the ```AvsGovernance``` contract, which handles the management of network members, deposits, and more. The network can control stake tokens based on task performance and vote against malicious actions. These votes are managed by the ```AttestationCenter``` contract, which monitors task performance, operators, and their stakes.

To address cost and availability concerns, ```AvsGovernance``` and ```AttestationCenter``` are deployed on separate networks, Layer 1 and Layer 2, respectively. The Othentic Stack leverages LayerZero messaging protocol, along with ```L1MessageHandler``` and ```L2MessageHandler```, to enable message-passing interactions across different layers.

## AVS Structure on Othentic Stack

The Othentic Stack enables developers to build an AVS by abstracting away common technical challenges and low-level infrastructure details. Developers focus solely on implementing the two key business actors of AVSs, "Performer" and "Attester" (collectively forming the validator), while their respective business logic is handled by off-chain services.

### Layer1 Components

The Layer 1 part, consists of the following contract deployments:
1. [Othentic Registry](https://docs.othentic.xyz/main/avs-framework/smart-contracts/othentic-registry) is a singleton smart contract that facilitates the integration with shared security protocols and AVSs. 
2. [AvsGovernance]() is governance contract of the AVS.
3. [l1MessageHandler](https://docs.othentic.xyz/main/avs-framework/smart-contracts/message-handlers#l1-message-handler) is used to send messages from the AVS governance contract to L2.

### Layer2 Components

The Layer 2 part, consists of the following contract deployments:
1. [AttestationCenter](https://docs.othentic.xyz/main/avs-framework/smart-contracts/attestation-layer) is a contract designed to ensure the integrity and efficiency of AVS operations by bridging off-chain execution with on-chain verification and maintaining a transparent history of all activities involved.
2. [OBLS](https://docs.othentic.xyz/main/avs-framework/smart-contracts/othentic-bls-obls) is the contract that facilitates on-chain verification for AVS tasks, enabling AVS’s Operators to submit distinct task specifications
3. ```BN256G2``` is cryptographic logical contract used by OBLS
4. [l2MessageHandler](https://docs.othentic.xyz/main/avs-framework/smart-contracts/message-handlers#l2-message-handler) is used to send messages from the Attestation center contract to L1.

## Install Othentic CLI

Install using npm:
```
npm i -g @othentic/othentic-cli
```

## Protocols/ Libraries Used
- [LayerZero](https://layerzero.network/)
- [libp2p](https://github.com/libp2p/js-libp2p)

