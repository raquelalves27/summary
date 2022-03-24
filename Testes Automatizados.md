# Testes Automatizados

Em primeira mão você pode achar que esta incompleto, uma explicação pra isso é: SIM EU AINDA ESTOU ESTUDANDO SOBRE ESSE ASSUNTO, MAS IREI COMPLEMENTAR ASSIM QUE POSSÍVEL,  E SE VOCÊ TB QUISER AJUDAR COM ESSA DOCUMENTAÇÃO, É SO ME MANDAR UM “ALÔ” QUE VOCÊ PODE VIRAR UM EDITORA(O). 😉

Esse tipo de **teste** é executado a partir de interações diretas com o código-fonte da aplicação.

Testa a sintaxe de um código. 

Testa a boa logica.

Testa alguma falha previsível.

## Teste de Unidade

**Teste de somente um método de uma classe.**

1. ARRANGE 

Preparação de um cenário de teste. (O que será executado).

1. ACT

A execução do cenário de teste. (O que realmente queremos testar na pratica )

 3. ASSERT 

Verificação se esta tudo correto e com retorno de ok, se não um retorno de erro. (Conteúdo esperado). 

### Exemplo

```jsx
<?php
**//ARRANGE**
$pessoa = new Pessoa('Raquel', new DataTimeImmutable(2003-10-27));
**//ACT**
$idadePessoa = $pessoa -> idade();
**//ASSERT**
$idadeEsperada = 22;

if ($idadeEsperada === $idadePessoa) {
   echo 'TESTE OK';
} else {
   echo 'TESTE FALHOU';
}
```

1- Criei uma pessoa que esta pronta pra ter a idade calculada.

2- Executo a ação que eu quero testar, que no caso é o calculo da idade;

3- Depois verifico se deu certo.

---

### TDD (Test-Driven Developmen)

É a ideia de você escrever o teste primeiro e deixar esse teste quebrado orientar o seu desenvolvimento.

Falhar e refatorar até passar, assim seria possível garantir que o que foi solicitado seria entregue no final, e testado.

Tudo deve ser testado antes de ser desenvolvido.

- write a failing test → `escrever um teste com falha`
- make the test pass → `fazer o teste passar`
- refactor → `refatorar`

[Se uma classe precisar ser testada e depender de outras classes que não devem ser alteradas ou controladas naquele momento, então é possível e necessário a criação de classes dubles.](POO%20259eb.md) Que realizaram o mesmo trabalho que as dependências reais, porem sem nenhum risco a aplicação.

---

## BDD (behavior Driven Development)

Comportamento da aplicação guia os testes.

- Começar o desenvolvimento de fora pra dentro
- como o usuário interage com a aplicação e deixar isso guiar a aplicação
1. Funcionalidae
2. Cenário 
3. Quando

Para poder ser testável, utilizamos **Critério de aceitação. Iniciando com as pré-condições (Given / Dado), seguindo por uma ação (When / Quando) é possível chegar a um comportamento como resultado esperado (Then / Então).**

### Exemplo :

```
Cenário 1:

Compra de um produto com frete grátis em região Sul do Brasil.

**Dado** que eu sou um cliente  

**Quando** eu comprar um produto de qualquer categoria  

**E** o valor total da compra for igual ou maior a R$ 100  

**E** meu CEP pertencer a região Sul  

**Então** eu vejo o frete grátis
```

---

## Teste de Integração

Normalmente são os testes que utilizamos mais de uma classe real. Um teste que realiza persistência no DB, que chama uma API externa. Um teste que combina a funcionalidade do seu código com algum sistema externo. 

## Teste Ponta a Ponta

Testar o sistema real em funcionamento. Significa rodar e testar tudo que a aplicação tem. 

MASSS em um ambiente controlado.

Comando para baixar PHPUnit

```jsx
composer require --dev phpunit/phpunit
```
