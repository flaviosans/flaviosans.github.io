---
layout: post
title: Angular - String vazia passada para getElementById()
date: 2020-03-09 08:22
summary: Esse é um erro chato, porém simples de ser resolvido!
categories: Angular Firefox
---

## O problema
Estava criando um formulário por esses dias, e quando testava me deparei com o seguinte erro no console do Firefox:

```String vazia passada para getElementById().```

poderia ser uma mensagem em inglês também:

```Empty String passed to getElementById()```

Não houve nenhuma quebra de página, nem outro problema sério, porém, incomoda. Mas a resolução é simples. Na página, havia um trecho do formulário assim: 

{% highlight html %}
<div class="field">
  <label class="label" for="">Data de nascimento: </label>
  <div class="control">
    <input class="input" [(ngModel)]="pessoa.dataDeNascimento" type="text">
  </div>
</div>
{% endhighlight %}

## A solução

Note que no label, no atributo `for=""` falta o preenchimento do id. Basta preencher com o id adequado, ou, caso não tenha, apagar o atributo `for=""` simplesmente! Para que o erro sumisse, eu tive que parar o `ng serve` e rodar novamente. Faça o teste.

Pronto! Se tiver alguma dúvida, ou se isso não resolver o seu problema, me deixe saber, coloque um comentário aqui!

Abraços, e bons códigos!