# Finalmente, que são as transações de Litecoin

Na primeira parte deste guia, nós conversamos rapidamente sobre o que são é um blockchain. Vamos relembrar rapidamente:

    Blocos são como pastas que guardam documentos com informações como quem enviou Litecoin e quanto foi enviado.
    Blockchain é uma estante com pastas (os blocos) que qualquer pessoa pode tem acesso.

<p align="center">
    <img src="img/folders.png"><br>
    <i>Uma forma de conceitualizar Blockchain</i>
</p>
    
Neste capítulo, daremos uma olhada apenas no essencial sobre o que exatamente ocorre quando você envia Litecoins da sua carteira.

## Finalmente, que são as transações Litecoin?

Uma transação Litecoin baseia-se em dois grupos de pessoas para ser bem sucedida e registrada definitivamente na Blockchain:

    Usuários
    Mineradores

Esses dois grupos de pessoas usam software clientes compatíveis com a blockchain, como o [Litecoin Core](https://www.litecoin.org), que não apenas funcionam como carteira mas também como uma cópia completa da blockchain Litecoin (full node, ou nó completo). É por isso que em [2. Entenda o que são as carteiras](02-Entenda_o_que_sao_as_carteiras.md) eu descrevi Litecoin Core como uma carteira de nó completo. We will now discuss the difference between User Full Nodes and Miner Full Nodes.

**Nós de Usuários**

No momento em que você baixa o Litecoin Core e sincroniza completamente a blockchain em seu computador, o seu Litecoin Core se torna um Nó Completo de Usuário. Nós de Usuários são importantes por causa de uma série de motivos: servem como estações de transmissão, validadores de registros, testemunhas e reguladores.

<p align="center">
    <img src="img/estacaotransmissao.png"><br>
    <i>Uma forma de conceitualizar o Litecoin Core, um nó completo</i>
</p>

Enquanto estação de transmissão, Nós de Usuários enviam informação uns para os outros, assim como as transaçes Litecoin que estão tentando ser processadas. Todos os nós, juntos, formam a rede Litecoin. Os nós também ajudam a proteger a blockchain, compartilhando uns com os outros sobre o quão rápido os mineradores finalizaram o bloco mais recente e se há nós se comportando de forma inadequada ou incompatível com a rede Litecoin.

Enquanto validadores de registros, Nós de Usuários baixam toda a blockchain. Isso quer dizer que cada nó possui a cópia de todo o livro-razão das transações realizadas desde o início do Litecoin. É por isso que as blockchains são consideradas descentralizadas. Muitas pessoas, não apenas uma, possuem todas as informações da rede Litecoin. Dessa forma, milhares de pessoas podem validar e verificar se as transações recebidas para processamento na rede Litecoin são ou não válidas.

Enquanto testemunha, Nós de Usuários garantem que haja apenas uma cópia da blockchain por meio de um processo chamado "consenso".  Se dois mineradores finalizam a adição de blocos ao mesmo tempo, os nós irão trabalhar coletivamente para escolher qual bloco irá compor a sequência "real" da blockchain. Normalmente, a sequência que adicionar 10 a 15 blocos primeiros é a vencedora. A sequência perdedora ficará orfã e será esquecida.

Enquanto reguladores, Nós de Usuários implementam e preservam a integridade da rede. Possuem a habilidade de implementar alterações no protocolo da blockchain, como o aumento do tamanho de bloco ou uma nova tecnologia (a exemplo da SegWit - Segregated Witness).

Mas, talvez, o mais imporante é que Nós de Usuários regulam e criam problemas matemáticos que os mineradores precisam resolver para conseguir adicionar blocos na blockchain. Se os mineradores estiverem resolvendo muito rápido, então os nós aumentam a dificuldade da equação. Se mineradores estiveram resolvendo muito devagar, então a dificuldade é diminuida. Esse processo é chamado "Prova-de-Trabalho" (Proof-of-Work, ou PoW) e é importante pois adiciona segurança à blockchain. Quanto mais difícil é a equação, mais difícil será para pessoas mál intencionadas acessarem a blockchain e maliciosamente tentar mudar alguma informação que lá está.

**Nós de Mineradores**

Mineradores fazem tudo que os usuáris fazem, mas também realizam a importante tarefa de "mineração". Isso quer dizer que eles criam, removem e adicionam blocos na blochain Litecoin. Para fazer isso, eles utilizam um nó completo (como o Litecoin Core) exatamente como os usuários, mas, em conjunto com o Litecoin Core, também utilizam um software de mineração conectado a um computador especializado na tarefa de resolver as equações da rede Litecoin - que é o processo de mineração. Esse conjunto de software e hardware permite adquirir as informações necessárias, como a dificuldade do bloco e as transaçes Litecoin, assim como transmitem a proposta de bloco selecionado para a rede Litecoin (e os nós decidirão se este é o bloco a ser adicionado na blockchain). Por essa razão, mineradores são recompensados financeiramente por seu trabalho com Litecoin toda vez que adicionam com sucesso um bloco à blockchain.

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
