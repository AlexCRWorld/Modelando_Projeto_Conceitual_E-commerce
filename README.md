# Bootcamp Geração Tech Unimed-BH - Ciência de Dados
## Projeto Banco de Dados - E-Commerce

1. Contexto: Levantamento de Requisitos
2. Projeto Conceitual: Modelo ER (Entidade Relacional)
3. Projeto Lógico: Modelo Relacional

### Levantamento de Requisitos

1.1. Escopo:
    
    - Produto;
    - Cliente;
    - Pedido;
    - Fornecedor;
    - Estoque;
    - Venda de produtos.

1.2. Narrativa:

    Produto: 
        
        - Os produtos são vendidos por uma plataforma online. Contudo, estes podem ter vendedores distintos (Terceiros);
        - Cada produto possui um fornecedor;
        - Um ou mais produtos podem compor um pedido.

    Cliente:

        - O cliente pode se cadastrar no site com seu CPF ou CNPJ;
        - O endereço do cliente irá determinar o valor do frete;
        - Um cliente pode comprar mais de um pedido. Este tem um período de carência para devolução do produto.

    Pedido: 

        - Os pedidos são criados por clientes e possuem informações de compra, endereço e status da entrega;
        - Um produto ou mais compõem o pedido;
        - O pedido pode ser cancelado.

    Fornecedor & Estoque:

        - Deverá haver um controle de quantidade de produtos disponíveis para venda.

    Venda de Produtos:

        ** Informação fornecida pela instituição na sessão de refinamento.

### Projeto Conceitual

2.1. Refinamento:

    - Cliente PJ e PF: Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
    - Pagamento: Pode ter cadastrado mais de uma forma de pagamento;
    - Entrega: Possui Status e Código de Rastreio.

### Projeto Lógico

3.1. Cliente PJ e PF:

    - Optei por fazer a criação de duas entidades: Pessoa Física e Pessoa Jurídica, como forma de separar seus atributos;
    - As entidades Cliente, Fornecedor e Terceiro - Vendedor herdarão os atributos PF ou PJ de acordo o tipo do cadastro, a partir de uma relação 1:1;
    - As entidades Clientes, Fornecedor e Terceiro - Vendedor possuem apenas um atributo que é o Tipo de Pessoa (Booleano) como forma de direcionamento para a herança de atributos PF ou PJ.

3.2. Pagamento:

    - Criei uma nova entidade com o nome de Pagamento e fiz o relacionamento com a entidade Pedido;
    - A relação criada entre as entidades foi de 1:N, pois entendo que um pedido pode ter diferentes formas de pagamento.

3.3 Entrega:

    - Criei uma nova entidade com o nome de Entrega e inclui os atributos de Status da Entrega e Código de Rastreio;
    - Fiz a relação de 1:1 da entidade Entrega com a entidade Pedido;
    - A entidade Entrega herdou o id do Pedido e o id do Cliente que já estava na entidade Pedido.