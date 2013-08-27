Introdução ao Sass.
===================

O Sass foi desenvolvido por Hampton Catlin, o mesmo criador do Haml.Seu principal objeto é adicionar poder ao CSS,
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



