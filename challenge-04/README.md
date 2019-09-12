# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function (x) {
  return !!x
}

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy(false)
isTruthy(undefined)
isTruthy(null)
isTruthy(NaN)
isTruthy(0)
isTruthy(-0)
isTruthy('')

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy(true)
isTruthy('0')
isTruthy(1)
isTruthy(12)
isTruthy(-1)
isTruthy({})
isTruthy([])
isTruthy(function () {})
isTruthy(20 * 30)
isTruthy(20 / 30)
isTruthy(0 + 1)
isTruthy(1 - 10)

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
  marca: "Renault",
  modelo: "Sandero",
  placa: "MMM-1234",
  ano: 2011,
  cor: "preto",
  quantasPortas: 5,
  assentos: 5,
  quantidadePessoas: 0,
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudarCor = function (novaCor) {
  this.cor = novaCor
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor = function () {
  return this.cor
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
carro.obterModelo = function () {
  return this.modelo
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function () {
  return this.marca
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
carro.obterMarcaModelo = function () {
  return "Esse carro é um " + this.marca + " " + this.modelo
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
carro.adicionarPessoas = function (numeroPessoas) {
  var totalPessoas = this.quantidadePessoas + numeroPessoas

  if (this.quantidadePessoas === this.assentos && totalPessoas >= this.assentos) {
    return "O carro já está lotado!"  
  }

  if (totalPessoas > this.assentos) {
    var pessoasCabem = this.assentos - this.quantidadePessoas
    var pessoaPluralOuSingular = pessoasCabem === 1 ? "pessoa" : "pessoas"
    return "Só cabem mais " + pessoasCabem + " " + pessoaPluralOuSingular + "!"
  }

  this.quantidadePessoas += numeroPessoas
  return "Já temos " + this.quantidadePessoas + " pessoas no carro!"
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.obterCor() // preto

// Mude a cor do carro para vermelho.
carro.mudarCor("vermelho")

// E agora, qual a cor do carro?
carro.obterCor() // vermelho

// Mude a cor do carro para verde musgo.
carro.mudarCor("verde musgo")

// E agora, qual a cor do carro?
carro.obterCor() // verde musgo

// Qual a marca e modelo do carro?
carro.obterMarcaModelo() // Esse carro é um Renault Sandero

// Adicione 2 pessoas no carro.
carro.adicionarPessoas(2) // Já temos 2 pessoas no carro

// Adicione mais 4 pessoas no carro.
carro.adicionarPessoas(4) // Só cabem mais 3 pessoas!

// Faça o carro encher.
carro.adicionarPessoas(3) // O carro já está lotado!

// Tire 4 pessoas do carro.
carro.adicionarPessoas(-4)

// Adicione 10 pessoas no carro.
carro.adicionarPessoas(10) // Só cabem mais 4 pessoas!

// Quantas pessoas temos no carro?
carro.quantidadePessoas // 1
```
