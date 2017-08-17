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


