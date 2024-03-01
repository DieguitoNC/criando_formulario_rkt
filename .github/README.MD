# Obs
Deixei todos os arquivos que utilizei tanto para estudo quanto para o projeto final.
Os arquivos de estudo / conhecimento inicial deixei na pastinha "docs"

# Imagem do projeto finalizado
![Imagem do projeto](<Screenshot 2024-02-29 225756.png>)

# Entendendo campos HTML 
# Campos formularios
```
<label for="text">Area de texto</label>

<input type="text" name="text " id="text">

  

<input type="password" name="password" id="password">

<input type="number" name="number" id="number">

<select name="" id="">

  <option value="color">Azul</option>

  <option value="team">Corinthians</option>

</select>

  

<textarea name="" id="" cols="30" rows="10"></textarea>
```
Comecar com input para definir os tipos
### Tipo
Qual o tipo da entrada de dados
### Nome - Name
Enviar o dado para o servidor / BD
### ID 
Serve para usar as propriedades no css
### Label
Serve para identificar o campo / nome do campo na imagem da tela e quando clicar redirecionar para o campo em questao

![[Pasted image 20240226175346.png]]
#### for
falar para que serve esse campo
tem que ter o mesmo nome do ID
![[Pasted image 20240226175443.png]]
### Input text
Vai abrir uma selecao que podemos colocar texto
### input password
Abre a opcao de colocar senha
### Input number
Abre a opcao de colocar um numero
### Select
Abre uma aba que podemos escolher entre os elemetos
#### Option
Sao as opcoes que disponibilizamos para o usuario acessar


## FORM vai criar o forms
## Action 
Onde o formulario vai ser enviado
## Methods
### Get
Receber e enviar recursos - no google 'e enviar a pesqusia
## Post 
Serve para enviar recursos
## Diferenca entre GET e POST
Normalmente o POST envia recursos pelo corpo (body) enquanto o GET envia pela URL.
# Como funciona os formularios
```
<form action="" method="post">

  <input type="text" name="q" id="">

  <input type="hidden" name="asasa" value="AS0aisEUQUEQOI_weqJDQDSAajsa-weqjweq">

  <input type="submit" value="Pesquisar">

</form>
```
Temos o comando que vai dar a acao quando clicarmos em enviar formulario, o tipo dele para escolha.
Alem disso, podemos esconder algum valor do usuario na hora que ele busca / da submit
Por ultimo o que realmente aparece para ele com o "Submit" no qual vai aparecer apenas pesquisar

# Iniciando os estilos de paginas
```
body::before {

  content: '';

  width: 100%;

  height: 368px;

  

  position: absolute;

  top: 0;

  left: 0;

  z-index: -1;

  background-color: #121214;

}
```
## ::before - pseudoclass
### CONTENT: AASASASA; 
Tem que usar sempre, mesmo para deixar em branco
### z-index vai deixar essa parte no eixo Z (3D)
Como queremos deixar ela de fundo, vamos deixar no -1

# Agrupando campos com fieldset e legend
```
    <form action="">

      <fieldset>

        <legend>Informações do evento</legend>

      </fieldset>

    </form>
```
## Fieldset 
vai criar o campo para o cabecalho
## Legend
Vai criar a legenda / texto do cabecalho


# Ajustando novos campos dentro do fieldset
## Bug do fieldset com legend
Quando a gente quer definir alguns parametros para o Fieldset, se houver o legend logo abaixo, nao ira aplicar para o legend.
Por isso precisamos criar uma nova div e incluir a partir do legend nela 
```
<fieldset>

        <div class="fieldset-wrapper">

          <legend>Informações do evento</legend>
```
# Estilizando o campo select
## Link para saber se funciona algumas funcionalidades no navegador 
https://caniuse.com/
## Transformar SVG para base  65
https://yoksel.github.io/url-encoder/
### SELECT - Para customizar o botao de selecionar no formulario
Temos uma artimanha quando queremos utilizar uma imagem no lugar daquele icone feioso
1. Primeiro de tudo vamos fazer ele desaparecer com os seguintes comandos
```
.input-wrapper select {

  appearance: none;
```
2. Agora temos que pegar uma imagem em svg e transformar ela para a base 65 e depois disso basta apenas tirar sua repeticao e posicionar corretamente
```
 background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none'%3E%3Cg clip-path='url(%23clip0_1_54)'%3E%3Cpath d='M8 10L12 14L16 10' stroke='%239C98A6' stroke-width='1.5' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_1_54'%3E%3Crect width='24' height='24' fill='white'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");;

  background-repeat: no-repeat;

  background-position: right 24px top 50%;
```
# Aplicando estilos aos agrupamentos
## > serve para chamar o elemento no css
## :nth-child vai chamar o enesimo filho, entao precisamos colocar um parametro
```
.col-3 > div:nth-child(1) {

  width: 100%;

}
```


# Checkbox customizado e com acessibilidade
## Criar com um input checkbox
No html criar um input com checkbox
## Checkbox - relative
```
.checkbox-wrapper {

  position: relative;

}
```
## Checkbox - label
Aqui vamos organizar / configurar o texto da label com o checkbox
```
.checkbox-wrapper label {

  display: flex;

  align-items: center;

  gap: 16px;

  margin: 0;

}
```
## input - checkbox
Aqyu vanis definir  o tamanho do checkbox e deixar com posicao absoluta. Para nao haver problema de acessibilidade e aparecer selecionado ao dar tab, para nao atrapalhar a estilizacao colocamos sua opacidade como zero
```
.checkbox-wrapper input {

  position: absolute;

  width: 24px;

  height: 24px;

  

  opacity: 0;

}
```
## label:before -> checkbox
Aqui vamos criar um quadrado estilizado para selecionar, o principal 'e deixar o content vazio e colocar display block. Depois basta pegar as configuracoes
```
.checkbox-wrapper label::before {

  content: '';

  width: 24px;

  height: 24px;

  display: block;

  
  

  border: 1px solid #E6E6F0;

  border-radius: 8px;

}
```

## input:checked + label::before
Nessa parte basicamente conseguimos garantir que quando for clicado a checkbox a imagem selecionada aparecera
```
checkbox-wrapper input:checked + label::before {

  background-image: url("data:image/svg+xml,%3Csvg width='26' height='26' viewBox='0 0 26 26' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Crect x='1' y='1' width='24' height='24' rx='8' fill='%23FAFAFC' stroke='%23E6E6F0'/%3E%3Cg clip-path='url(%23clip0_5018_21)'%3E%3Cpath d='M10 17.17L5.83 13L4.41 14.41L10 20L22 8L20.59 6.59L10 17.17Z' fill='%2342D3FF'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_5018_21'%3E%3Crect width='24' height='24' fill='white' transform='translate(1 1)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E%0A");;

}
```

##  input:focus + label::before
Nessa ultima etapa de estilizacao, quando estiver encima do botao o mouse ou o "tab", conseguimos fazer acontecer algo, nesse caso deixamos um contorno 
```
.checkbox-wrapper input:focus + label::before {

  outline: 2px solid black;

  

}
```
# Criando estilos para o submit
## Como eu quero estilizar eu crio um footer
## Customizacao do footer
- Aqui basicamente posso colocar todas as propriedades que preciso fazer 
```
footer {

  background: #F0F0F4;

  

  height: 136px;

  

  display: flex;

  flex-direction: column;

  
  

  padding: 40px 64px;

  

  margin-bottom: 100px;

  

  border-top: 1px solid #D6D6D6;

  border-radius: 0 0 8px 8px;

}
```
- Reoara qye ora cruar a "Divisao" entre o forms e o "submit" estilizamos a border top 
- Tabem colocamos display flex pra alinhar, porem queremos alinhar em coluna ao inves de linha
## Estilizando o Button
- Aqui basicamente vamos pegar e colocar as propriedades do Button e dps fazer um "hover" classico
```
footer {

  background: #F0F0F4;

  

  height: 136px;

  

  display: flex;

  flex-direction: column;

  
  

  padding: 40px 64px;

  

  margin-bottom: 100px;

  

  border-top: 1px solid #D6D6D6;

  border-radius: 0 0 8px 8px;

}

  

footer .button {

  height: 56px;

  border-radius: 8px;

  background: #04D361;

  

  border: 0;

  font-family: Archivo;

  font-size: 16px;

  font-weight: 600;

  line-height: 26px;

  

  color: white;

}

  

footer .button:hover {

  background: #077c3c;

  

}
```
# Validando campos e submetendo formularios
## required e outras propriedades
- Serve para deixar o campo como obrigatorio
- min length, max length serve para obrigar ter minimo ou maximo de caracteres, etc
```
<div class="input-wrapper">

            <label for="event-password">Senha de acesso para os participantes <span>(mínimo 8 caracteres)</span></label>

            <input

            type="password"  

            id="event-password"

            required

            minlength="8">

          </div>
```
## Submit do formulario
### Botao de formulario automaticamente vira submit
- Para usar um botao normal a gente tem que classificar como
```
<button type="button"</button>
```
- Ou input type button
```
<input type="button" value="teste"/>
```