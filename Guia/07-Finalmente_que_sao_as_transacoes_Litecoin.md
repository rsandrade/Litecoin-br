# Finalmente, que são as transações de Litecoin

Na primeira parte deste guia, nós conversamos rapidamente sobre o que são é um blockchain. Vamos relembrar rapidamente:

    Blocos são como pastas que guardam documentos com informações como quem enviou Litecoin e quanto foi enviado.
    Blockchain é uma estante com pastas (os blocos) que qualquer pessoa pode tem acesso.

<p align="center">
    <img src="img/folders.png"><br>
    <i>Uma forma de conceitualizar Blockchain</i>
</p>
    
Neste capítulo, daremos uma olhada apenas no essencial sobre o que exatamente ocorre quando você envia Litecoins da sua carteira.

## What’s in a Litecoin Transaction Anyway?

Uma transação Litecoin baseia-se em dois grupos de pessoas para ser bem sucedida e registrada definitivamente na Blockchain:

    Usuários
    Mineradores

Both of these groups of people use reference clients like Litecoin Core because it not only functions as a wallet, but also as a full node. This is why in Understanding Wallets I described Litecoin Core as a full node wallet. We will now discuss the difference between User Full Nodes and Miner Full Nodes.

Users Nodes

The moment you download Litecoin Core and completely sync with the blockchain, your Litecoin Core becomes a User Full Node. Now User Nodes are important because they have several jobs. They serve as relay stations, record keeping validators, witnesses, and regulators.
One way to conceptualize Litecoin Core, a full node

As relay stations, User Nodes send information to one another such as Litecoin transactions that are trying to get processed. In this way, all nodes compose the Litecoin network. They also help secure the blockchain by sharing with one another how fast miners have solved the most recent block and if there are any nodes that are misbehaving.

As record keeping validators, User Nodes download the whole blockchain. That means every single full Litecoin node has a copy of the ledger. This is why blockchains are considered decentralized. Many people, not just one, have access to the information. In this way, thousands of people can validate and verify that the Litecoin transactions being sent on the network are valid.

As witnesses, User Nodes make sure that there is only one copy of the blockchain through a process called “consensus.” Should two miners end up adding blocks at the same time, the nodes will collectively work together to choose which one is the “real” chain. One way they do this is by watching to see which chain adds blocks faster. Typically, the first chain to add 10–15 blocks is the winner. The losing chain then gets orphaned and forgotten.

As regulators, User Nodes implement and preserve the integrity of the network. They have the ability to implement changes in blockchain protocol such as increasing the blocksize or implementing new technology such as Segregated Witness.

But perhaps most importantly, User Nodes regulate and create mathematical problems that miners have to solve in order to add their block to the blockchain. If they solve it too quickly, then these nodes increase the difficulty of the equation. If miners solve it too slowly, then they decrease it. This process, which is called “Proof of Work,” is important because it adds security to the blockchain. The more difficult the equation, the harder it is for people to access the blockchain and maliciously try to change information in it.

Miner Nodes

Miners do everything Users do but also perform the important task of “mining.” This means they create, solve, and add blocks to the Litecoin blockchain. In order to do this, they utilize a full node like Litecoin Core just like Users. However, they also run a separate mining software attached to a mining specific computer and then “point” it to Litecoin Core. This allows them to gather necessary information, such as block difficulty and Litecoin transactions, as well as to broadcast their proposed block to the Litecoin network. For this reason, miners are financially rewarded with Litecoins for their work every time they successfully add a block to the blockchain.

As block creators, a miner chooses a single transaction and creates a coinbase. The miner then utilizes this coinbase to create a potential block to be added to the blockchain. He is incentivized to fill this block with as many transactions as possible because he gets all their transaction fees.

As block solvers, a miner focuses his computational power on solving the lock equation the nodes have created.

If he is the first person to solve it, he is given permission to add his block onto the blockchain and reap the block reward (currently at 25 Litecoins).

Now what happens when two or more miners solve the lock equation at the same time? Well we would have two blockchains with different information in it. This is unacceptable as all the nodes require “consensus.” Therefore, nodes will typically observe which blockchain grows the fastest to choose that one as the authentic Litecoin blockchain.

Ok,now let’s review step by step how it all works from the beginning:

    You send a LTC transaction from your wallet-node.
    The transaction is broadcast to the network and is labeled “unconfirmed” because it is not on the validated by the full nodes on the network yet.
    Miners choose 1 transaction to create a block and fill it with other transactions that have been broadcast.
    Miners solve the lock equation to earn the right to add their block to the blockchain.
    When he is successful, the transaction is officially recorded. Once more blocks are added to the chain and are validated by all the nodes, it is labeled as “confirmed.”
