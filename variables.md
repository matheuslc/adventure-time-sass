Variáveis
=========

Variáveis armazenam valores que podem ser utilizados a qualquer momento do seu código, dependendo do escopo em que ela se encontra.

Para criar, você digita o caracter $ (dollar), seguido de seu nome.

```scss

$nome-da-variavel: "Hello World";

```

## !default flag

Como o nome já fiz uma variável pode conter dados diferentes a qualquer momento, mas só pode conter um dado, e para evitar uma sobre-escritra de dados
 é utilizado o flag !default.
Este !flag dirá o seguinte: Se não houver nenhum dado na variável, então será inserido o dado, caso haja, não será atribuido o valor.

#### O problema:

```scss
// Neste exemplo, o dado irá sobre-escrever a variável.

$base-color: #fffff;

$base-color: #00000;

.text {
color: $base-color; // Cor #00000

}

```

#### A solução:

```scss
// Neste exemplo, o dado não irá sobre-escrever, pois já tem um dado na variável.

$base-color: #fffff;

$base-color: #00000 !default;

.text {
color: $base-color; // Cor #fffff;

}
```

## Tipos de dados

As variáveis podem conter diferentes tipos de dados, como:

##### Booleanos
```scss
$rounded: true;
$shadow: false;
```

##### Números (com ou sem ponto)

```scss
$rounded: 10px;
$line-height: 1.5;
```

##### Cores

```scss
$base: red;
$border: rgba(0,255,0,0.5);
$shadow: #333;

```

##### Strings

```scss
// Pode ser sem aspas, aspas duplas ou simples

$text: "Hello World";
$message: Real World ? ;

```

##### Listas

```scss
$names: matheus,lucas,gabriel,ronaldo;
$margin: 40px 15px 15px 20px;

```

##### Null

```scss
$shadow: null;
```


Escopo
======

O escopo de uma variável é o contexto onde ela foi definida, pode ser um escopo global, ou local. Vamos aos exemplos.

##### Escopo Local
A variável poderá ser usada apenas no bloco de códio em que ela foi declarada.


```scss
p {
    $border: #333;
    border-top: $border;
}


// Se você tentar usar a variável em outro elemento, será gerado um erro.

h1 {
  border-top: $border; // ERRO
}

```

##### Escopo Global

Quando a variável é declarada fora de qualquer bloco de código, ela é considerada global, então você poderá usar em qualquer lugar.

```scss

$border: #333;


p {
    
    border-top: $border;
}

// Agora você pode usá-la em qualquer local.

h1 {
  border-top: $border;
}

```



