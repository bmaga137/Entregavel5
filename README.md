# NOMES DOS INTEGRANTES DA EQUIPE: 

Bruno Magalhães - 2520504

# DEFINIÇÃO DO SISTEMA

O AutoParts Store é um sistema web de comércio eletrônico desenvolvido para uma loja especializada na comercialização de peças e acessórios automotivos, atendendo clientes que desejam realizar a manutenção, substituição ou personalização de seus veículos.

O sistema tem como principal objetivo facilitar o processo de busca, seleção e compra de peças automotivas, oferecendo uma plataforma intuitiva, organizada e segura.

A aplicação permitirá que os clientes visualizem os produtos disponíveis, consultem informações detalhadas, verifiquem preços e disponibilidade em estoque, adicionem produtos ao carrinho e realizem pedidos de compra.

Além disso, o sistema contará com uma área administrativa destinada ao gerenciamento dos produtos, categorias, estoque, clientes, pedidos e transações comerciais.

O sistema será desenvolvido utilizando tecnologias web modernas, com separação entre frontend e backend, comunicação por meio de serviços REST e armazenamento de dados em um banco de dados SQLite.

# LISTA DE FUNCIONALIDADES

## 2.1.	Funcionalidades do cliente

> Cadastro de usuários. Login e logout.
> Autenticação e autorização de acesso. Edição de informações pessoais.
> Consulta ao catálogo de peças automotivas. Pesquisa de produtos por nome ou descrição. Filtragem de produtos por categoria.
> Visualização de detalhes dos produtos.
> Consulta de preços e disponibilidade em estoque. Adição de produtos ao carrinho de compras.
> Remoção de produtos do carrinho. Alteração da quantidade de produtos. Cálculo automático do valor total da compra. Finalização de pedidos.
> Simulação de métodos de pagamento. Registro de transações comerciais.
> Visualização do histórico de pedidos. Consulta do status dos pedidos.

## 2.2.	Funcionalidades administrativas
 
> Login administrativo. Cadastro de novos produtos.
> Edição de produtos existentes. Exclusão ou desativação de produtos. Gerenciamento de categorias.
> Atualização dos preços dos produtos. Gerenciamento do estoque.
> Consulta de produtos disponíveis e indisponíveis. Visualização de clientes cadastrados.
> Consulta de pedidos realizados. Atualização do status dos pedidos. Consulta das transações realizadas.
> Visualização de informações gerais sobre as vendas.

## 2.3.	Funcionalidades relacionadas às transações

Criação de pedidos de compra.
Registro dos produtos associados a cada pedido. Cálculo do subtotal e valor total.
Verificação da disponibilidade dos produtos. Validação das quantidades solicitadas.
Registro da forma de pagamento escolhida. Simulação da aprovação ou rejeição de pagamentos.
Atualização do estoque após a confirmação da compra. Armazenamento do histórico das transações.
Cancelamento de pedidos conforme suas regras de negócio.
Controle dos estados da transação: pendente, aprovada, recusada e cancelada.

# CARACTERÍSTICAS DO SISTEMA

## 3.1.	Usabilidade

O sistema deverá possuir uma interface intuitiva, organizada e de fácil utilização, permitindo que os usuários encontrem rapidamente as peças automotivas desejadas e realizem suas compras sem dificuldades.

## 3.2.	Segurança

O sistema deverá implementar mecanismos de autenticação e autorização, garantindo que cada usuário tenha acesso somente às funcionalidades permitidas pelo seu perfil.

As senhas deverão ser armazenadas utilizando algoritmos seguros de hash.

As operações administrativas deverão ser protegidas contra acessos não autorizados.

## 3.3.	Integridade dos dados
 
O sistema deverá garantir a consistência das informações armazenadas, principalmente durante as operações de compra, atualização de estoque e registro de transações.

As operações críticas deverão utilizar transações do banco de dados para evitar inconsistências.

## 3.4.	Organização

A aplicação deverá apresentar uma separação lógica entre frontend, backend, regras de negócio e camada de persistência de dados.

## 3.5.	Disponibilidade de informações

Os usuários deverão conseguir consultar informações atualizadas sobre produtos, preços e disponibilidade em estoque.

## 3.6.	Responsividade

A interface deverá adaptar-se a diferentes tamanhos de tela, incluindo computadores, tablets e dispositivos móveis.

## 3.7.	Manutenibilidade

O código deverá ser organizado em módulos, componentes e serviços, facilitando futuras modificações, correções e implementação de novas funcionalidades.

# TECNOLOGIAS UTILIZADAS

## 4.1.	Frontend

HTML: estruturação das páginas.
CSS: estilização e organização visual da interface.
JavaScript: implementação de comportamentos e funcionalidades interativas. React: construção da interface por meio de componentes reutilizáveis.

## 4.2.	Backend

Node.js: execução de serviços e funcionalidades do lado do servidor. 
Django: desenvolvimento de serviços e regras de negócio utilizando Python.
Web Service REST: comunicação entre frontend e backend por meio de requisições HTTP. Rotas: organização dos endpoints responsáveis pelas operações do sistema.

A arquitetura deverá definir claramente as responsabilidades de Node.js e Django, evitando duplicação de funcionalidades e regras de negócio.

## 4.3.	Controle de acesso
 
Autenticação: identificação e validação da identidade dos usuários.
Autorização: definição das permissões de acesso de acordo com os perfis de usuário. Perfis previstos:
Cliente. Administrador.

## 4.4.	Sistema Gerenciador de Banco de Dados (SGBD)

SQLite: armazenamento das informações do sistema.

O banco de dados deverá armazenar informações relacionadas aos usuários, produtos, categorias, estoque, carrinhos, pedidos, itens dos pedidos e transações.

# PRINCIPAIS ENTIDADES DO SISTEMA
O banco de dados deverá contemplar, inicialmente, as seguintes entidades: Usuário: informações dos clientes e administradores.
Produto: informações das peças e acessórios automotivos. Categoria: classificação dos produtos.
Estoque: quantidade disponível de cada produto. Carrinho: produtos selecionados pelo cliente.
ItemCarrinho: produtos e quantidades associados ao carrinho. Pedido: informações gerais de cada compra.
ItemPedido: produtos, quantidades e preços registrados no pedido. Transação: informações sobre o processamento do pagamento.

# REGRAS DE NEGÓCIO

Somente usuários autenticados poderão finalizar compras. Cada usuário poderá consultar seu próprio histórico de pedidos.
Somente administradores poderão cadastrar, editar e remover produtos.
Não será permitida a compra de quantidades superiores ao estoque disponível. O valor total do pedido deverá ser calculado automaticamente.
Os preços registrados nos itens do pedido deverão representar os valores praticados no momento da compra.
O estoque deverá ser atualizado após a confirmação da compra. Um pedido deverá possuir pelo menos um item.
Toda compra deverá gerar um registro de pedido.
As transações deverão possuir um status que represente sua situação atual.
Operações de compra e atualização de estoque deverão preservar a integridade dos dados.

# MÉTODOS E OPERAÇÕES DE TRANSAÇÃO

O sistema deverá disponibilizar operações para:
 
createOrder(): criação de um pedido. addOrderItem(): inclusão de produtos no pedido. calculateTotal(): cálculo do valor total.
validateStock(): verificação da disponibilidade em estoque. processPayment(): processamento ou simulação do pagamento. updateStock(): atualização das quantidades disponíveis. confirmOrder(): confirmação do pedido.
cancelOrder(): cancelamento do pedido. getOrderHistory(): consulta do histórico de compras. getTransactionStatus(): consulta do status da transação.

As operações que envolvem confirmação da compra, registro do pedido e atualização do estoque deverão utilizar transações atômicas no banco de dados, garantindo que todas sejam concluídas corretamente ou revertidas em caso de falha.

# OBJETIVO FINAL

O objetivo final do AutoParts Store é oferecer uma solução digital que facilite a comercialização de peças automotivas, simplificando a experiência de compra dos clientes e proporcionando aos administradores ferramentas para controlar produtos, estoque, pedidos e transações.

O sistema deverá demonstrar, por meio de um protótipo funcional, o fluxo completo de uma compra, desde a seleção dos produtos até a confirmação e o registro da transação.
