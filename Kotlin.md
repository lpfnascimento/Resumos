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

~~~~
fun main()
{
    println("Bem Vindo ao Bytebank")
    //testaLacos()
    var conta01 = Conta()//instancia da classe = usando variavel para poder fazer impressao
    conta01.titular = "Lúcia"
    conta01.numero = 1010
    conta01.setSaldo(1000.00)
    println("Titular: ${conta01.titular}")
    println("numero: ${conta01.numero}")
    println("saldo: ${conta01.getSaldo()}")


    var conta02 = Conta()
    conta02.titular = "Thiago"
    conta02.numero = 1020
    conta02.setSaldo(25000.10)
    println("Titular: ${conta02.titular}")
    println("numero: ${conta02.numero}")
    println("saldo: ${conta02.getSaldo()}")

//    println("\n Depositos:\n")
//    println("Titular: ${conta01.titular}")
//    conta01.deposito(800.00)
//    println("saldo: ${conta01.saldo}")
//
//
//    conta02.deposito(10000.00)
//    println("Titular: ${conta02.titular}")
//    println("saldo: ${conta02.saldo}")
//
//    println("\n Sacar\n")
//    println("Titular: ${conta01.titular}")
//    conta01.sacar(10000.00)
//    println("saldo: ${conta01.saldo}")
//
//    conta02.sacar(20000.00)
//    println("\n Titular: ${conta02.titular} ")
//    println("saldo: ${conta02.saldo}")
//
//
//    println("\n Tranferencia\n")
//    println("\n Tranferencia: Conta02 para Conta 01\n")
//    if(conta02.transferencia(100000.00 , conta01)){
//        println("tansferencia realizada com sucesso")
//    }else
//        println("Erro: operação mal sucedida")
//    println("saldo conta 02: ${conta02.saldo}")
//    println("saldo conta 01: ${conta01.saldo}")
}

class Conta
{
    var titular = ""
    var numero = 0
    private var saldo = 0.0

    //metodo ou tb chamado Comportamento
    fun deposito ( valor: Double)
    {
        this.saldo += valor
    }
    fun sacar (valor: Double)
    {
        if(valor <= this.saldo)
            saldo -= valor
    }
    fun transferencia(valor: Double, destino: Conta) : Boolean//conta que chama a função não precisa ser declarada - já é verificada
    {
        if (saldo >= valor){
            saldo -= valor
            destino.deposito(valor)
            return true
        }else
            return false

    }
    fun getSaldo(): Double {
        return saldo
    }
    fun setSaldo(valor: Double){
        if(valor > 0){
            saldo = valor
        }
    }
}

fun testaCopiasEReferencias ()
{
    val contaJoao = Conta() //joao aponta p conta - instancia
    contaJoao.titular = "joão"
    var contaMaria = contaJoao //conta Maria aponta p conta joao (esta aponta p classe conta - maria aponta p conta)
    //contaMaria e contaJoao compartilham mesma instancia nesse caso; jeito de resolver é cada um ter sua instancia
    contaMaria.titular = "Maria Martha" // vaor passado por referencia - mudei direto no campo de titular

    println("Conta do João: ${contaJoao.titular}")
    println("Conta da Maria: ${contaMaria.titular}")
    //ambas vão imprimir Maria Martha porque o valor foi passado por referencia
    //quando lida com objetos: valores mudados por referancia e não por copia - cuidado com as atribuições
}

fun testaLacos()
{
    var i = 0
    while (i < 4)
    {
        val titular = "Liliane $i"
        val numeroConta = 1000 + i
        var saldo = 10.0 + i
        println(" titular: $titular \n numero da conta: $numeroConta \n saldo: $saldo ")
        testaCondicao(saldo)
        println()
        i++
    }
}

fun testaCondicao(saldo: Double)
{
    if (saldo > 0.0) {
        println("saldo positivo!!!!")
    } else if (saldo == 0.0) {
        println("saldo neutro")
    } else {
        println("saldo negativo!!!!")
    }
}
~~~~
~~~~
fun main() {
    println("Bem Vindo ao Bytebank")
    //testaLacos()
    var conta01 = Conta(titular = "Lucia", numero = 1010)//instancia da classe = usando variavel para poder fazer impressao
    //conta01.titular = "Lúcia"
    //conta01.numero = 1010
    conta01.deposito(1000.00)
    println("Titular: ${conta01.titular}")
    println("numero: ${conta01.numero}")
    println("saldo: ${conta01.saldo}")
//labels = colocar nome parametro na instancia permite que não seja na ordem de inicializacao e visualize melhor -
    //quando declara um label tem que declarar outros

    var conta02 = Conta("Thiago", 1020) //instancia com parametros  - classe construtora
    //conta02.titular = "Thiago" //intancia sem parametros
    //conta02.numero = 1020
    conta02.deposito(25000.00)
    println("Titular: ${conta02.titular}")
    println("numero: ${conta02.numero}")
    println("saldo: ${conta02.saldo}")

    println("\n Depositos:\n")
    println("Titular: ${conta01.titular}")
    conta01.deposito(800.00)
    println("saldo: ${conta01.saldo}")


    conta02.deposito(10000.00)
    println("Titular: ${conta02.titular}")
    println("saldo: ${conta02.saldo}")

    println("\n Sacar\n")
    println("Titular: ${conta01.titular}")
    //conta01.sacar(10000.00)
    println("saldo: ${conta01.saldo}")

    // conta02.sacar(20000.00)
    println("\n Titular: ${conta02.titular} ")
    println("saldo: ${conta02.saldo}")


    println("\n Tranferencia\n")
    println("\n Tranferencia: Conta02 para Conta 01\n")
    /* if(conta02.transferencia(100000.00 , conta01)){
         println("tansferencia realizada com sucesso")
     }else
         println("Erro: operação mal sucedida")
     println("saldo conta 02: ${conta02.saldo}")
     println("saldo conta 01: ${conta01.saldo}")*/
}

class Conta(
    var titular: String,
    val numero: Int
) { //construtor primario - parametros como properties
    var saldo = 0.0
        private set
//         set(valor) {//field = acessa valor de propertie e que muda o valor
//            if (valor > 0) {
//                field = valor
//            }
//        }

    /*Classe Construtora - construtor secundario*/
//    constructor(titular: String, numero: Int){
//        this.titular = titular
//        this.numero = numero
//    }

    //metodo ou tb chamado Comportamento
    fun deposito(valor: Double) {
        if (valor > 0) {
            this.saldo += valor
//            }
        }
        fun sacar(valor: Double) {
            if (valor <= this.saldo)
                saldo -= valor
        }

        fun transferencia(
            valor: Double,
            destino: Conta
        ): Boolean//conta que chama a função não precisa ser declarada - já é verificada
        {
            if (saldo >= valor) {
                saldo -= valor
                destino.deposito(valor)
                return true
            } else
                return false

        }
//    fun getSaldo(): Double {
//        return saldo
//    }
//    fun setSaldo(valor: Double){
//        if(valor > 0){
//            saldo = valor
//        }
//    }
    }

//    fun testaCopiasEReferencias() {
//        val contaJoao = Conta() //joao aponta p conta - instancia
//        contaJoao.titular = "joão"
//        var contaMaria = contaJoao //conta Maria aponta p conta joao (esta aponta p classe conta - maria aponta p conta)
//        //contaMaria e contaJoao compartilham mesma instancia nesse caso; jeito de resolver é cada um ter sua instancia
//        contaMaria.titular = "Maria Martha" // vaor passado por referencia - mudei direto no campo de titular
//
//        println("Conta do João: ${contaJoao.titular}")
//        println("Conta da Maria: ${contaMaria.titular}")
//        //ambas vão imprimir Maria Martha porque o valor foi passado por referencia
//        //quando lida com objetos: valores mudados por referancia e não por copia - cuidado com as atribuições
//    }

    fun testaLacos() {
        var i = 0
        while (i < 4) {
            val titular = "Liliane $i"
            val numeroConta = 1000 + i
            var saldo = 10.0 + i
            println(" titular: $titular \n numero da conta: $numeroConta \n saldo: $saldo ")
            testaCondicao(saldo)
            println()
            i++
        }
    }

    fun testaCondicao(saldo: Double) {
        if (saldo > 0.0) {
            println("saldo positivo!!!!")
        } else if (saldo == 0.0) {
            println("saldo neutro")
        } else {
            println("saldo negativo!!!!")
        }
    }
}
~~~~
