# Catalog-v1
## Descrição do componente: 
Este componente terá uma interface que lista a estrutura mercadológica cadastrada na Bookstore. Usa NativeQueryLanguage que possibilita a busca e filtragem dos itens. 
## Motivação: 
Durante o desenvolvimento de Bookstore, alguma parte pode precisar acessar o catálogo para uso, desde criação de promoções com produtos, categorias e marcas até criação de componentes visuais que focam em um nicho específico de merdado.
## Interfaces
### IConnection
+ SecureConnection connect()
### ICatalog
+ getAll(String query, int page, int resultPerPage)
+ getOnlyCategories(String query, int page, int resultPerPage)
+ getOnlyOffers(String query, int page, int resultPerPage)


# Pagamento por cartão de crédito
## Descrição do componente: 
Componente responsável por realizar uma interface de comunicação entre uma aplicação qualquer e um intermediador de pagamentos. Todos os dados são recebidos e retornados via JSON para facilitar a integração com qualquer tipo de aplicação, seja ela Mobile ou Web, independentemente da linguagem utilizada no desenvolvimento, flexibilizando também, os dados retornado pelo intermediador de pagamentos.
## Motivação
Aplicações que necessitam a realização de pagamentos via Cartões de Crédito/Débito via um intermediador de pagamentos.
## Interfaces 
### Requerida
### IConnection
+ SecureConnection connect()
### Provida
### IExecutePayment
+ PaymentTransaction payWithCreditCard(CreditCardInfo card, Order order)
+ PaymentTransaction payWithCreditCard(CreditCardInfo card, Consortium order)


# Conector com Intermediador de pagamento
## Descrição do componente: 
Este componente disponibiliza uma interface para  conexão com intermediadores de pagamentos via API.
## Motivação
Para centralizar a conexão com o intermediador de pagamentos.
## Interfaces 
### Provida
### IConnection
+ SecureConnection connect()


# Perfil de Compra
## Descrição do componente: 
Este componente oferece a possibilidade de parceiros consumirem nossos dados de analises de compra para direcionarem melhor suas estratégias de marketing.
Nossa API fornece toda a experiência que nossos clientes tiveram no nosso site durante seu processo de compra alem de dados como um status de possível comprador, comprador ou comprador assiduo.
Para cosumir estes dados basta enviar o numero do cpf do cliente e nosso sistema fará uma análise dinámica devolvendo em tempo ábil uma gama de dados úteis para qualquer vendedor online.
## Motivação
Aplicações que desajam consumir experiências de usuários para direcionar melhor suas campanhas de marketing online.
## Interfaces 
### Requerida
### IConnect
+  Connect()
### Provida
+ GetProfile()
Retorna um array com os dados baseado no CPF enviado na conexão.
+ GetProfileDetail(Detail:Boolean)
Retorna um array com todos os dados da experiencia do usuário baseado no CPF enviado na conexão.

# Sugestao de Produto
## Descrição do componente:
Este componente é responsável por sugerir livros que estão no catalógo do BookStore com base
no histórico de compras do cliente, visualização de conteúdo e perfil. 
## Motivação
Tem como principal beneficio impulsionar as vendas do ecommerce e sugerir potenciais livros que o cliente possa
se interessar.
## Interfaces
### Requeridas
### IPerfilCliente
+ retorna uma lista de dados do cliente como sexo, idade, endereço e grupo de consórcio (se fizer parte).
### IHistoricoCompra
+ Retorna o histórico de compras de produtos especificos do cliente no ecommerce.
### IHistoricoVisita
+ Retorna o historio de produtos visualizados pelo cliente no ecommerce.
### Provida
+ sugerirProduto
Sugere produtos da BookStore com base no perfil, historico de compra e produtos visualizados pelo cliente.
