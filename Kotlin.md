#Atalhos
ctrl /  comenta código e descomenta
crtl + alt + l formata codigo
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
