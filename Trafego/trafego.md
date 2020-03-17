### Payloads
#### Base 'A'
> - Nome
> - Usuário
> - Senha
> - CPF
> - Endereço
> - Lista de dívidas
> - Contatos
> - Filiação
> - Log de alterações
> - Dados bancarios

#### Base 'B'
> - Idade
> - Lista de bens
> - Endereço
> - Fonte de Renda
> - Estado civil
> - Possui restrição

#### Base 'C'
> - Ultima Consulta do CPF
> - Movimentação financeira
> - Ultima compra


### Services
##### O tráfego dos dados pode ser realizados através de serviços ligado em sua respectiva base.
#### Base 'A' e Base 'B' - GOlang
###### - Para essa situação utilizaria micro-serviços, onde o mesmo se relaciona diretamente com sua base, acionado através de um gateway.
###### - A comunicação pode ser hibrida, podendo usar API para ações do tipo get e post, e algumas ações de inserçao ou alteração (insert, update e delete), onde não necessitar resposta imediata, pode ser realizada via mensageria.
###### - Esses serviços seriam responsáveis por validações, criptografia, comunicação com a base, entre outras atividades relacionadas aos seus dados.
###### - Acrescentaria também o envio dessas informações para um Data Lake.
##### Em relação a autenticação, poderia ser usado um nano-serviço unicamente com essa responsabilidade, já que os dados poderão ser acessados pelo cliente ou mesmo por outros algoritmos, no caso da base 'B'.

#### Base 'C' - Python
###### - Devido ao baixo teor de criticidade e necessidade de alta disponibilidade, utilizaria um micro-serviço com autenticação simples. 
###### - Comunicação apenas via API.

### Formato optado para manipulação dos dados:
#### - Json



