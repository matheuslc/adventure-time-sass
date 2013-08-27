#### Variáveis

Vocẽ pode armazenar cores,proriedades,strings e etc em variáveis, tornando o css modular e facilitando alterações, vamos a um exemplo:


```sass
// Criando a variável, no escopo em que ela se encontra ela é uma variável global

$base-color: #029fd3; 

.home {
  background-color: $base-color;
}

```

##### Facilitando alterações, como assim?
Veja só, agora queremos alterar o background do .home para uma cor roxa. Baste trocar na variável, assim:


```sass

$base-color: #a500ff;

.home {
  background-color: $base-color; // Temos uma cor roxa agora
}

```

Neste contexto o uso de variáveis parece inútil, mas pare e pense um site muito grande, com cores em vários lugares,
se um dia houvesse uma alteração e fosse necessário mudar todas as cores, seria mais fácil alterar uma variável, do que várias linhas de código.


