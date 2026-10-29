# Roteador de Entregas e Frota Urbana (logistica rapida)

  Nosso grupo vai desenvolver, em PHP, um sistema de despacho de entregas urbanas em tempo real, voltado para motoboys e entregadores. O sistema recebe os pedidos na central, roteiriza os destinos em um mapa da cidade, controla a carga de cada entregador e gera estatísticas de produtividade da frota.

  Escolhemos a Opção B (Web Simplificada com PHP + HTML/CSS). Vamos fazer um painel de controle visual, sem JavaScript e sem banco de dados SQL, como as regras do projeto exigem.

  Nosso painel tem formulários para cadastrar entregas e entregadores, e cada ação alimenta uma estrutura de dados (fila, vetor ou pilha) e é salva em arquivo, para que o sistema funcione como uma central de despacho de verdade.

  Cadastro de entregas (pedidos): um formulário recebe os dados do pacote (endereço/coordenadas X e Y no mapa, prioridade). Ao salvar, o pedido entra no final da fila de despacho e é gravado no arquivo.

  Cadastro de entregadores: outro formulário registra nome, identificação e status (Disponível, Em Rota ou Em Pausa). Eles ficam guardados no vetor de entregadores, e o status pode ser alterado depois pelo painel.

  Despacho e mochila: o sistema pega o primeiro pedido da fila e atribui a um entregador disponível. O pacote vai para a pilha dele, e as entregas são feitas do topo para baixo.


## 🚀 Funcionalidades

- Fila (FIFO) - Os pedidos chegam à central e ficam aguardando um entregador livre. O primeiro pedido a entrar é o primeiro a ser despachado, como em uma fila real de atendimento.

- Pilha (LIFO) -  Representa a mochila do entregador. Os pacotes são empilhados na ordem inversa da rota, então o último pacote colocado no topo é o primeiro a ser entregue.

- Matriz 2D - O mapa da cidade será dividido em quadrantes (linhas = X, colunas = Y). Nele vamos marcar a central, a posição dos entregadores e os pontos de entrega.

- Vetor 1D - Será a lista de entregadores cadastrados, cada um com seu status: Disponível, Em Rota ou Em Pausa.

- Busca e Ordenação:

•	Ordenação: os pacotes serão ordenados por prioridade e por distância até o destino. A distância será calculada a partir das coordenadas na matriz.

•	Busca: o usuário poderá localizar uma entrega pelo código de rastreio, usando busca linear.


## 🛠️ Tecnologias Utilizadas

- [HTML5]: O HTML5 será empregado na construção da arquitetura de conteúdo do sistema, priorizando elementos semânticos que asseguram a acessibilidade e o cumprimento das boas práticas de desenvolvimento web.

- [CSS]: Utilizaremos CSS para a estilização do sistema, aplicando regras responsivas para garantir perfeita adaptação a diferentes tamanhos de tela.

- [PHP]: O PHP atuará como a camada de backend responsável por toda a lógica de negócio do sistema. Ele manipulará em memória a fila de pedidos (FIFO), a pilha da mochila dos entregadores (LIFO), a matriz 2D do mapa urbano e o vetor 1D da frota. Além disso, o PHP executará os algoritmos de ordenação de pacotes (por prioridade e distância) e busca linear (por rastreio), processando as requisições e renderizando o painel visual sem dependência de banco de dados SQL ou JavaScript.# roteador-de-entregas-
