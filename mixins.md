Mixins
======

Os mixins vieram para combater a repetição de código desnecessário.
Com mixins, você cria blocos de códigos e pode usar apenas importanto estes blocos de códigos.

```scss
// Criamos um mixin 

@mixin button {
  border: 1px solid #ccc;
  font-size: 1rem;
  text-transform: uppercase;

}

.btn-a {
 @include button;
 background-color: #000;

}

.btn-b {
 @include button;
 background-color: #002ase;

}

```

NOTA: Para usar um mixins você utiliza o @include, para importar arquivos você usa o @import.

Este é um exemplo básico de uso de mixin, porém, agora veremos realmente seu poder.

### Parâmetro

Você pode passar um parâmentro em um mixins, o que é fenomenal, veja um exemplo.

```scss
// Quando você coloca um valor no parâmetro ele se torna o valor padrão, caso não seja inserido nenhum parâmetro, o padrao será esse.
@mixin box-sizing($x: border-box) {
  -webkit-box-sizing: $x;
  -moz-box-sizing: $x;
  box-sizing: $x;

}

.content {
  @include box-sizing(border-box);
  padding: 20px;
  border: 1px solid #000;
}

```

Você também pode passar mais de um parâmetro para sua função.

```scss

@mixin button($radius, $color) {
  border-radius: $radius;
  color: $color;

}

.btn-a {
  @include button(10px,#3333);
  }

```

#### Paramêtros com ,(vírgula).

Se você tentar passar um parâmetro com vírgulas, exemplo:

```scss
@mixin transition($x){
    transition: $x;  
  }

.btn-a{
   @include transition(color 0.3s ease-in, background 0.5s ease-out); // Repare na vírgula que separa as propriedades.
}

```
Isso irá gerar um erro, pois o Sass irá entender que você passou dois parâmetros, quando no caso, apenas 1 era preciso.

##### Ta, mas e agora?

Para isso criamos um parâmetro variável.

Mas, como? Assim:

```scss
// Os 3 pontos após a variável
@mixin transition($x...){
    transition: $x;  
  }

.btn-a{
   @include transition(color 0.3s ease-in, background 0.5s ease-out);
}

```

## Um bom problema que pode ser resolvido com um bom mixin

```scss
@mixin highlight-t($color){
    border-top-color: $color;
  }

@mixin highlight-b($color){
    border-bottom-color: $color;
  }

@mixin highlight-l($color){
    border-left-color: $color;
  }



.btn-a{
   @include higlight-r(#f00);
}

```

Temos vários mixins separados, porque
queremos diferentes lados. Para resolver isso, podemos usar Interpolation. Vejamos:

```scss
@mixin highlight($color, $side){
    border-#{$side}-color: $color;
  }

 .btn-a {
  @include highlight(#f00, right);
 }

 .btn-b {
  @include highlight(#f00,left);

 }
```
