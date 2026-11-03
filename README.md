# AutoParts Store

Sistema web de comércio eletrônico para uma loja especializada na venda de peças e acessórios automotivos.

## Sumário

- [Integrantes](#integrantes)
- [Visão geral](#visão-geral)
- [Funcionalidades](#funcionalidades)
- [Características do sistema](#características-do-sistema)
- [Tecnologias utilizadas](#tecnologias-utilizadas)
- [Principais entidades](#principais-entidades)
- [Regras de negócio](#regras-de-negócio)
- [Operações de transação](#operações-de-transação)
- [Objetivo final](#objetivo-final)

## Integrantes

- **Bruno Magalhães** — 2520504

## Visão geral

O AutoParts Store tem como objetivo facilitar a busca, a seleção e a compra de peças automotivas. A plataforma permitirá que clientes consultem produtos, preços e disponibilidade em estoque, adicionem itens ao carrinho e realizem pedidos.

O sistema também contará com uma área administrativa para o gerenciamento de produtos, categorias, estoque, clientes, pedidos e transações comerciais.

A aplicação será desenvolvida com tecnologias web modernas, separação entre frontend e backend, comunicação por serviços REST e armazenamento em banco de dados SQLite.

## Funcionalidades

### Cliente

- Cadastrar-se, entrar e sair do sistema.
- Autenticar-se e editar informações pessoais.
- Consultar o catálogo de peças automotivas.
- Pesquisar produtos por nome ou descrição e filtrar por categoria.
- Visualizar detalhes, preços e disponibilidade dos produtos.
- Adicionar e remover produtos do carrinho e alterar quantidades.
- Calcular automaticamente o valor total da compra.
- Finalizar pedidos e simular métodos de pagamento.
- Registrar transações comerciais.
- Consultar o histórico e o status dos pedidos.

### Administração

- Realizar login administrativo.
- Cadastrar, editar, excluir ou desativar produtos.
- Gerenciar categorias, preços e estoque.
- Consultar produtos disponíveis e indisponíveis.
- Visualizar clientes cadastrados e pedidos realizados.
- Atualizar o status dos pedidos.
- Consultar transações e informações gerais sobre vendas.

### Pedidos e transações

- Criar pedidos e registrar os produtos associados.
- Calcular subtotal e valor total.
- Verificar a disponibilidade dos produtos e validar as quantidades solicitadas.
- Registrar a forma de pagamento escolhida e simular a aprovação ou rejeição do pagamento.
- Atualizar o estoque após a confirmação da compra.
- Armazenar o histórico das transações.
- Cancelar pedidos conforme as regras de negócio.
- Controlar os estados da transação: **pendente**, **aprovada**, **recusada** e **cancelada**.

## Características do sistema

### Usabilidade

A interface deverá ser intuitiva e organizada, permitindo que os usuários encontrem rapidamente as peças desejadas e realizem compras com facilidade.

### Segurança

- Implementar autenticação e autorização de acordo com o perfil de cada usuário.
- Armazenar senhas usando algoritmos seguros de hash.
- Proteger operações administrativas contra acessos não autorizados.

### Integridade dos dados

O sistema deverá manter a consistência dos dados, especialmente durante compras, atualizações de estoque e registros de transações. Operações críticas deverão utilizar transações do banco de dados para evitar inconsistências.

### Organização e manutenibilidade

A aplicação deverá separar logicamente frontend, backend, regras de negócio e persistência de dados. O código deverá ser organizado em módulos, componentes e serviços para facilitar modificações, correções e a inclusão de novas funcionalidades.

### Disponibilidade de informações

Os usuários deverão consultar informações atualizadas sobre produtos, preços e disponibilidade em estoque.

### Responsividade

A interface deverá adaptar-se a diferentes tamanhos de tela, incluindo computadores, tablets e dispositivos móveis.

## Tecnologias utilizadas

### Frontend

- **HTML** — estruturação das páginas.
- **CSS** — estilização e organização visual da interface.
- **JavaScript** — comportamentos e funcionalidades interativas.
- **React** — construção da interface com componentes reutilizáveis.

### Backend e comunicação

- **Node.js** — execução de serviços e funcionalidades no servidor.
- **Django** — desenvolvimento de serviços e regras de negócio em Python.
- **Web Service REST** — comunicação entre frontend e backend por requisições HTTP.
- **Rotas** — organização dos endpoints responsáveis pelas operações do sistema.

A arquitetura deverá definir claramente as responsabilidades de Node.js e Django, evitando a duplicação de funcionalidades e regras de negócio.

### Controle de acesso

- **Autenticação** — identificação e validação da identidade dos usuários.
- **Autorização** — definição das permissões de acordo com o perfil.
- **Perfis previstos:** cliente e administrador.

### Banco de dados

- **SQLite** — armazenamento das informações do sistema.

O banco deverá armazenar informações sobre usuários, produtos, categorias, estoque, carrinhos, pedidos, itens dos pedidos e transações.

## Principais entidades

O banco de dados deverá contemplar inicialmente as seguintes entidades:

| Entidade | Responsabilidade |
|---|---|
| **Usuário** | Informações de clientes e administradores. |
| **Produto** | Informações das peças e dos acessórios automotivos. |
| **Categoria** | Classificação dos produtos. |
| **Estoque** | Quantidade disponível de cada produto. |
| **Carrinho** | Produtos selecionados pelo cliente. |
| **ItemCarrinho** | Produtos e quantidades associados ao carrinho. |
| **Pedido** | Informações gerais de cada compra. |
| **ItemPedido** | Produtos, quantidades e preços registrados no pedido. |
| **Transação** | Informações sobre o processamento do pagamento. |

## Regras de negócio

- Somente usuários autenticados poderão finalizar compras.
- Cada usuário poderá consultar apenas o próprio histórico de pedidos.
- Somente administradores poderão cadastrar, editar e remover produtos.
- Não será permitida a compra de quantidades superiores ao estoque disponível.
- O valor total do pedido deverá ser calculado automaticamente.
- Os preços registrados nos itens do pedido deverão corresponder aos valores praticados no momento da compra.
- O estoque deverá ser atualizado após a confirmação da compra.
- Todo pedido deverá possuir pelo menos um item.
- Toda compra deverá gerar um registro de pedido.
- As transações deverão possuir um status que represente sua situação atual.
- As operações de compra e atualização de estoque deverão preservar a integridade dos dados.

## Operações de transação

O sistema deverá disponibilizar as seguintes operações:

| Operação | Descrição |
|---|---|
| `createOrder()` | Criação de um pedido. |
| `addOrderItem()` | Inclusão de produtos no pedido. |
| `calculateTotal()` | Cálculo do valor total. |
| `validateStock()` | Verificação da disponibilidade em estoque. |
| `processPayment()` | Processamento ou simulação do pagamento. |
| `updateStock()` | Atualização das quantidades disponíveis. |
| `confirmOrder()` | Confirmação do pedido. |
| `cancelOrder()` | Cancelamento do pedido. |
| `getOrderHistory()` | Consulta do histórico de compras. |
| `getTransactionStatus()` | Consulta do status da transação. |

As operações de confirmação da compra, registro do pedido e atualização do estoque deverão utilizar transações atômicas no banco de dados. Assim, todas serão concluídas corretamente ou revertidas em caso de falha.

## Objetivo final

O AutoParts Store busca oferecer uma solução digital que facilite a comercialização de peças automotivas, simplifique a experiência de compra dos clientes e forneça aos administradores ferramentas para controlar produtos, estoque, pedidos e transações.

Por meio de um protótipo funcional, o sistema deverá demonstrar o fluxo completo de uma compra, desde a seleção dos produtos até a confirmação e o registro da transação.
