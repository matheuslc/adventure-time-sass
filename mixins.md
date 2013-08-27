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
