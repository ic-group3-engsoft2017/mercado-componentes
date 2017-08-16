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
Este requer uma interface para conexão com o provedor de serviço de pagamento onde dados de conexão serão enviados e validados. Ele disponibilizará  a interface para envio dos dados de pagamento de um cliente onde o mesmo receberá um retorno do sucesso ou não da integração.
## Motivação
Para as oepraçes realizadas com um intermediador de pagamentos, e se necessário, fácil de remover e colocar outro sem redeploy da aplicação central.
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


