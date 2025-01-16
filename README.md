# Refinando um modelo conceitual de um projeto de E-commerce
Refinando um modelo inicial de banco de dados de uma plataforma de E-commerce - DIO Heineken 

# Requisitos
Os produtos são vendidos por uma única plataforma online, mas podem ter vendedores distintos dentro dela. Cada produto possui apenas um fornecedor e produtos podem compor um pedido. Produtos são mantidos em um ou mais estoques em diferentes locais.
Clientes podem se cadastrar com CPF ou CNPJ. O endereço dos clientes determina o frete do pedido. Clientes podem comprar mais de um pedido.
Pedidos são criados por clientes e possuem informações como compra, endereço e status de entrega. Um produto ou mais compoem o pedido e o pedido pode ser cancelado.

# Refinamentos propostos
## Uma conta pode ser PJ ou PF, mas não pode ter as duas informações
Esse requisito foi contemplado a partir da especialização disjunta de cliente entre Pessoa Física e Pessoa Jurídica. Essas subclasses possuem a identificação adequada e um id.
## Clientes podem cadastrar mais de uma forma de pagamento
Para este requisito, criou-se uma nova entidade "Forma de pagamento" que agrupa as formas de pagamentos reistradas pelos clientes, incorporando o ID do cliente responsável por ela (consequência do relacionamento "registra" 1-N entre forma de pagamento e cliente). "Forma de pagamento", então, paga um pedido, que por sua vez incorpora o id da forma de pagamento que foi utilizada.
## Informações como status de entrega e código de rastreio devem ser registradas
Optei por defini-los como atributos do pedido, tendo em vista que refletem na condição do pedido e não "agregam" suficientemente para gerar a entidade "entrega", no entanto, pode ser uma outra opção de modelagem sem desdobramentos negativos.
