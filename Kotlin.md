
#Atalhos
*ctrl /  comenta código e descomenta
*crtl + alt + l formata codigo
* Você pode fazer manualmente ou usar o atalho Ctrl + Alt + M do IntelliJ para usar o Extract Function.
*  Conta.kt ou usar o atalho do IntelliJ Alt + Enter e escolher a opção Extract 'Conta' from current file.
*  “Alt + Shift + X = fecha todos arquivos
*   “Alt + Enter” =  Put Parameters on Separate Lines, que vai colocar cada um desses parâmetros em linhas separadas.
*   F5 = copia classe mas muda nome; interessante em heranças
*   "ctrl + b" : quando quer saber onde a classe está no codigo, seleciona classe e clica crtl b
*   "ctrl + n" : faz busca das classes no projeto
*   "ctrl + alt +o" : organiza automaticamente os pacotes (não usados e usados)
*   "ctrl + h": mostra hierarquia
# Variables
* mutável (var)
* imutável (val) -não modifica valor depois que foi inicializada a variavel

#### kotlin tem a peculiaridade de ter que inicializar com valor a variavel; se não tem definido o valor: usar val que pode modificar ao longo do programa. 
* para modificar valor, tem que ser do mesmo tipo: 0.0 para 100.0 (e não 100 - kotlin não permite)

## Primitive data types
* int , double
* Long, short, byte

### Floating-point and other types
* Double, float, char (1 caracter) , boolean
* string (+ de uma caracter);

## declaração de função:
* necessário indicar tipo do parâmetro;
  *  ex: fun testasaldo (saldo : Double){}
## Aprendemos que existem 2 construtores no Kotlin: o primário e o secundário. Em situações que desejamos executar trechos de código a mais, o construtor secundário é mais interessante. Caso seja só inicialização, o construtor primário é o esperado.
### Toda vez que tem um construtor secundário, tem que fazer a invocação do primário; 


# Herança
### declarando
* class NomeClass (parameters - são var da classe mae/mais: variveis classe filha): NomeClasseMae(properties); open = open na classe mãe permite que a classe faça herança.
* overriding = colocado em metodos que são o mesmo da classe mãe porém precisam de um modificação especifica para a classe filha
* assinaturas de metodos da classe deve ser diferente como no java
* super = é o que permeite reutilizar um metodo existente e também fazer uma modificação sobre este método. 
* quando se replica demais um código é sinal de que te outro jeito para realizar;
* classes filhas utilizam de métodos da classe mae - então pode usar um método mais generico possivel quando se quer abranger todas as heranças; 
* porém, quando se quer algo mais específico, não pode usar algo generico. Por exemplo, filhas podem usar metodo mãe - porem mae n~çao pode usar metodo filha;

### Polimorfismo: 
#### para trab com polimorfismo, deve trabalhar com metodos genéricos encontrados na classe-mãe; não vai conseguir trabalhar com metodos especifcos de cada classe filha!!!
* utilizar o mesmo método generico da classe-mãe para entidades/instancias diferentes(filhas da classe mae)
* conseguimos trabalhar com diferentes instâncias que tem o mesmo tipo em comum e dessa maneira, conseguimos reutilizar os comportamentos que são comuns entre esse tipo, que é comum entre elas. No caso, o funcionário.
* conseguimos mandar apenas uma única referência na assinatura e conseguimos enviar várias instâncias diferentes, mas que herdam do mesmo tipo.
* O principal motivo, como podemos ver é que conseguimos reutilizar exatamente o mesmo código em comportamentos comuns entre a classe mãe e os seus filhos, que é o caso do uso da bonificação. Dado que a bonificação é comum para qualquer funcionário, nós conseguimos fazer operações com ela, mandando apenas a referência do funcionário.

### Abstrata
* estrutura que vai servir como base para todos, mas é uma estrutura abstrata; é uma estrutura que nós não vamos criar de verdade. Nós só vamos usar como base para reutilizar.
* funcionario não representa algo concretona vida real - funcionario, gerente: eles representam uma estrutura, denominação;
* quando usa ** abstract ** não precisa mais do **open** - está implicitoquando escreve abstract; 
* sempre terá que implementar -nomear as futuras instancias; ex:classe abstratafuncionario: não tem mais funcionario - precisa nomear qual cargo: faxineiro, analista, etc. Mas ele usa todas as properties da classe abstrata funcionario
* métodos devem ser tb abstratos; Outro detalhe é sumir com a implementação: contas, comportamentos das funções/metodos: será apenas referenciada. ex: fun bonificação, fun recompensa. 
* a paritr da classe abstrata, qualquer classe é obrigada a usar uma implementção do metodo da classe abs mae.

##Projeto em pacotes
* regras de negocios guardada na pasta modelos; - package
*  qunado arquivo que preciso não está no mesmo pacote é usado import
~~~
//import modelo.Analista
//import modelo.CalculadoraBonificacao
//import modelo.Diretor
//import modelo.Gerente
import modelo.* //jeito mais prático
~~~
### alias (as)
* util quando quero importar algo e que é muito grande e pretendo gerar apelido / como tb em conflito de classe com nomes iguais
~~~
import java.lang.String as StringJava

fun main() {
    val palavra: String = ""
    val palavraJava: StringJava = StringJava("")
}
~~~
## Build tools
* responsavel por automatizar tarefas rotineiras de um projeto - organiza e evita perder tempo; ** automatização e produtividade **
   * adicionar uma nova biblioteca, 
   * realização de testes, 
   * empacotamento e deploy,
   * compatibilidade entre as diversas IDEs
   * 
## Composição = um atributo da classe aponta para outra classe;
* **vantagem = mais autonomia para o código**
* quando um atributo de uma classe aponta para outra classe; Ex: titular classe conta aponta para classe cliente, que tem todos os dados de cliente. 
* independencia de criar atributos em uma classe e a outra só apontar para essa classe.
* Se possível, é melhor usar composição ao inves de herança. Porque se mudar uma classe, não altera a outra. No caso de herança, é carregado atributos e comportamentos e uma mudança interfere em outros pontos do código. 
* Com o uso da composição, o relacionamento é a classe ter outra, portanto, ela não vai ter as características da classe que a compõe, e sim a possibilidade de utilizá-la ou não.

## Object declarations
**procurar mais sobre e aprender bem o assunto**

## Exceptions
* para tratar exception, lnaça exceptions. Isso é feito em uma classe no kotlin - throwable; 
#### try -catch para pegar exception
- ClassCastException;
- ArithmeticException;
- NumberFormatException.

### ler mais sobre exceptions e safe call e fazer resumo
~~~~
try {
    // some code
} catch (e: SomeException) {
    // handler
} finally {
    // optional finally block
}
~~~~
### Init
- usado quando tem um construtor primario e deseja executar um tarefas na instancia na classe, em kotlin:
  -  unit
  -  construtor secundário
- **init faz verificacoes imediadas das properties da classe assim que esta é inicializada**
- The init block is always called after the primary constructor
-  class file can have one or more init blocks executing in series i.e. one after another.

## Nulls
- tipos comuns são não nulos por padrão
- "?" -> indica q var aceita nulos 

### !!
- Converte o tipo para um tipo not-null e caso o valor seja nulo resulta em NullPointerException.
~~~
fun strLen(value: String?) = value!!.length
strLen(null)
// NullPointerException
~~~
### Operador Elvis “?:”
- Este operador valida se um objeto é nulo e provê uma forma de devolver um valor default:
~~~
fun retrieveAdjective(value: String?) = value ?: "awsome"
val adjective = retrieveAdjective(null)
println("kotlin is $adjective!")
// kotlin is awsome!
~~~
