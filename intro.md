Introdução ao Sass.
===================

### Syntactically Awesome Stylesheets

Sass é um pré-processador de CSS, foi desenvolvido por Hampton Catlin, o mesmo criador do Haml, que é um pré-processador de HTML. Seu principal objeto é adicionar poder ao CSS,
de forma a deixar o desenvolvimento mais fácil.
Ele foi escrito em Ruby, outra alternativa ao Sass, escrito em javascript é o LESS. 

Algumas features que o Sass nos proporciona:

##### Variáveis
##### Nested
##### Mixins
##### Combinar arquivos sem perder performance
##### Entre outras ...


.sass ou .scss
--------------

O Sass nos fornece estas duas sintaxes. Por padrão usaremos o .scss que é a atual e mais utilizada por desenvolvedor.
Vamos as difereças das sintaxes:

### .scss

```scss
$base-color: #ff0000;
$secondary-color: #5e0606;
$base-text-color: #fff;
$margin: 10px;

article {
  background-color: $base-color;
  margin: $margin;
  font-family: 'Arial';
}

section {
  background-color: $secondary-color;
  font-family: 'Arial';
  color: $base-text-color;

}

```

### .sass

```sass
$base-color: #ff0000
$secondary-color: #5e0606
$base-text-color: #fff
$margin: 10px

article 
  background-color: $base-color
  margin: $margin
  font-family: 'Arial'


section 
  background-color: $secondary-color
  font-family: 'Arial'
  color: $base-text-color

```

Quando usamos .sass não precisamos colocar ;(ponto e vírgula) e nem chaves, porém temos que seguir uma regra de identação.


## Mas ... como funciona o Sass, já que o browser renderiza arquivos .css e não .scss.

O Sass é pré-processador de css, você escreve seu código utilizando toda a mágica que o Sass nos oferece, então ele processa
e gera um arquivo .css que pode ser interpretado pelo browser. Lindo não? 

##### Este código escrito em Sass, ao ser compilado irá gerar o css que é mostrado abaixo.

```scss
$blue: #3bbfce;
$margin: 16px;

.content-navigation {
  border-color: $blue;
  color:
    darken($blue, 9%);
}

.border {
  padding: $margin / 2;
  margin: $margin / 2;
  border-color: $blue;
}


```

##### Este é o css gerado.

```css

.content-navigation {
  border-color: #3bbfce;
  color: #2b9eab;
}

.border {
  padding: 8px;
  margin: 8px;
  border-color: #3bbfce;
}

```

Comentários no Sass
-------------------

Comentários são importantes para um melhor entendimento do códigoe documentação (porém há casos de códigos bem escritos que não necessitam de comentários).

O Sass nos fornece 2 maneiras de escreve de comentários, um que será compilado junto com o código, e outro que não será.

```scss
// Este comentário não irá aparecer após compilado

/* Este IRÁ aparecer */

```

Imports com Sass
----------------

Algo realmente bom que o Sass nos fornece é a possibilidade de modularizar o css e usar o Import para juntar o css depois 
e de maneira a não perder performance.
Mas antes, vamos entender porque a maneira de importação nativa perde performance.

Para importar arquivos css dentro de outros css nativamente, usamos o @import.

```css
@import url("buttons.css");

```
O problema é que quando o navegador renderizar a página, ele irá baixar todos os arquivos importados e só após baixar todos ele irá carregar o estilo do site.
E isso, claro irá aumentar o tempo que o site leva para abrir para o usuário.

##### Já no Sass ...

Lembra que o Sass pré-compila o css, então, ele compila todos os arquivos importados para o outro, cria o arquivo final e então está pronto.
Todo o códio está em uma página, deixando o carregamento da página mais rápido e seu css modularizo (o que com certeza irá manter o códgo organizado e a manutenção será 'beeeeem' mais fácil).

Sintaxe do Import:

```scss
@import "buttons";

// O Sass irá procurar o arquivo buttons e irá importar.
/* Há uma coisa que você precisa saber, no Sass você tem arquivos com _ (underline), esses arquivos não será criados
na versão final, são considerados PARTIALS. */

```


```scss
// Arquivos _buttons.scss;

.btn {
  background-color: #0093bc;
  border: 0;
}

```

```scss
// Arquivos style.scss;

.btn {
  background-color: #0093bc;
  border: 0;
}

```
