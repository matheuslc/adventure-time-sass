Extend
======

O Extend permite você estender uma classe, para assim reaproveitar propriedades que você iria repetir em outra classe. Vamos à um problema, e logo em seguida a sua solução:

#### O problema
Reparem neste trecho de código. Temos dois botões, e os dois usam 3 propriedades iguais. Podemos melhor isso usando o Extend.

```css
  .btn-a {
  	background: #777;
  	border: 1px solid #ccc;
  	font-size: 1rem;
  	text-transform: uppsercase;
  }

  .btn-b {
  	background: #ff0;
  	border: 1px solid #ccc;
  	font-size: 1rem;
  	text-transform: uppsercase;
  }

```
### A solução

```scss
 .btn-a {
  	background: #777;
  	border: 1px solid #ccc;
  	font-size: 1rem;
  	text-transform: uppsercase;
  }

  .btn-b {
  	@extend .btn-a ;
  	background: #ccc;
  }

```
Ele irá pegar todas as propriedades do botão A e sobre-escrever o background para o botão B, assim reaproveitando código.