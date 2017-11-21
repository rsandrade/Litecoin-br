# Finalmente, que são as transações de Litecoin

Na primeira parte deste guia, nós conversamos rapidamente sobre o que são é um blockchain. Vamos relembrar rapidamente:

- Blocos são como pastas que guardam documentos com informações como quem enviou Litecoin e quanto foi enviado.
- Blockchain é uma estante com pastas (os blocos) que qualquer pessoa pode tem acesso.

<p align="center">
    <img src="img/folders.png"><br>
    <i>Uma forma de conceitualizar Blockchain</i>
</p>
    
Neste capítulo, daremos uma olhada apenas no essencial sobre o que exatamente ocorre quando você envia Litecoins da sua carteira.

## Finalmente, que são as transações Litecoin?

Uma transação Litecoin baseia-se em dois grupos de pessoas para ser bem sucedida e registrada definitivamente na Blockchain:

- Usuários
- Mineradores

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

Enquanto criador de blocos, um minerador escolhe uma única transação e cria uma sequência de moedas. O minerador utiliza essa sequência para criar um bloco em potencial. Ele é incentivado a preencher esse bloco com o máximo possível de transações e, caso esse bloco seja adicionado à blockchain, ele receberá todas as taxas de transação.

Enquanto solucionadores de blocos, um minerador mantém o foco do seu poder computacional (o hardware de mineração) direcionado à tarefa de resolver, no menor tempo possível, a equação que os nós da rede estabeleceram.

Se um minerador for o primeiro a resolver a equação, é dada a ele a permissão para adicionar o bloco na blochain e receber a recompensa do bloco (atualmente 25 Litecoins.

O que acontece quando dois ou mais mineradores resolvem a equação ao mesmo tempo? Bem, nós teremos duas blockchain com diferentes informações nela. Isso é inaceitável, considerando que todos os nós precisam entrar em consenso quanto à blockchain "oficial". Assim, os nós normalmente observam qual blockchain cresce mais rápido e automaticamente escolhem uma como sendo a blockchain Litecoin autêntica.

Ok, vamos revisar, passso-a-passo, como tudo funciona desde o início:

- Você faz uma transação LTC da sua carteira.
- A transação é transmitida para toda a rede e é identificada como "não confirmada" ("unconfirmed"), pois não foi validada pelos nós completos da rede Litecoin ainda.
- Mineradores escolhem 1 transação para criar um bloco e completam a proposta de bloco com outras transações que foram transmitidas.
- Mineradores resolvem a equação e ganham o direito de adicionar o bloco proposto na blockchain Litecoin.
- Quando um bloco é adicionado com sucesso, as transações que fazem parte dele estarão oficialmente registradas e logo será identificada como "confirmada".
