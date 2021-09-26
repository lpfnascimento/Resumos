# Banco de Dados Relacionais

### Entidades
* Representa uma **coisa** ou **objeto** do mundo real com uma existência independente;
* existência física ou conceitual
* possui atributos;
* **Atributos** descrevem entidade
#### Atribrutos Simples ou compostos
* compostos: que pode desmembrar/divididos em mais atributos. Pdem formar hierarquia. 
    * ex: endereço {lougradouro, cep, cidade, estado...}, logradouro: {numero, complemento...}
* Simples: que não pode desmembrar/dividir - chamado tb de  **atômico**.
    * ex: rua do endereço;

#### Atributos Único valor ou Multivalorados
* único: unico valor para entidade. ex: definir para carro uma unica cor;
* multivalorado: pode ter mais de uma valor o mesmo atributo. Ex: form academica: nenhuma, uma ou várias...; cor de carro: uma, duas, três ... (pode restrigir qtidade de atibutos)

#### Atributos Armazenados e Derivados
* Derivado: quando um atributo é proveniente de outro atributo. Ex: idade, pode ser obtida da diferença dos atrib data atual e data nascimento; contagem de entidades q usam atrib, ex: num dunc depart.
* Armazenado: valor que vai ser colocado diretamente dentro do cadastro da entidade. ex: data de nascimento. 

#### Atributo NULL
* quando um valor não é aplicavel.
* ex: form academica = pessoa pode não ter; carro= pessoa pode não ter; complemento = pessoa pode morar em casa. 

## Atributos chaves e entidade fraca
* atributo chave são aqueles que definem uma entidade, eles são únicos e servem para identificar uma entidade
* Entidade fraca é aquela que não possui atributos chave. 

## Especialização e Generalização
* quando atributos podem ser diferentes dependendo da especificação; Ex: funcionario, pode ser tercerizado ou clt (os atributos para ambos serão diferentes). 

### Relacionamentos

* costuma usar verbo para relacionar 2 oumais entidades; são papeis atribuidos a entidade e forma que elas se relacionam.
* quando um atributo tem ligação com uma entidade, pode existir um relacionamento. 

#### grau de um relacionamento: 
* numero de entidades que participam de um relacionamento;
* Binário = 2 entidades relacioadas
* ternário = 3 entidades relacionadas

#### Relacioamentos Recursivos:
*  relacionamento que envolve duas entidades que são a mesma coisa;
*  ex: funcionário que supervisiona outro funcionário, nós não vamos construir no nosso diagrama de entidade e relacionamento duas entidades diferentes 
chamadas funcionário, criar um losango entre elas, há um recursividade, uma entidade se relaciona com ela mesma.

### Cardinalidade
* razão de cardinalidade: máximo de uma e máximo da outra
* uma maneira legal de detectar a cardinalidade é por meio do diagrama de venn. 

