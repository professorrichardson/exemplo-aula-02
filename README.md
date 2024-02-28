# Aula 02 continuação do cronometro ALURA


Vamos continuar programando nosso site?

# Conteúdo Principal
Vá para o arquivo style.css e abra o Live Preview para visualizar as estilizações que vamos fazer agora no nosso projeto.

Caso você tenha dúvida sobre como iniciar o Live Preview e Live Server, volte na atividade Preparando o ambiente: Live Server e Live Preview, da aula 1, onde ensinamos como utilizar esse recurso.

Vamos dar os primeiros passos na estilização do nosso conteúdo. Para fazer isso, vamos acessar a classe 'conteúdo principal' e inserir o seguinte código:

>Caso você tenha dúvida sobre como iniciar o Live Preview e Live Server, volte na atividade Preparando o ambiente: Live Server e Live Preview, da aula 1, onde ensinamos como utilizar esse recurso.

Vamos dar os primeiros passos na estilização do nosso conteúdo. Para fazer isso, vamos acessar a classe 'conteúdo principal' e inserir o seguinte código:
~~~css
.conteudo-principal {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
}
~~~

# O que esse código faz?
* display: flex; flex-direction: column, justify-content: center, align-items: center: alinha e centraliza os itens com os comandos;
* max-width: define uma largura máxima para nossa página de 1200px;
* width: 100%: ocupa a largura 100% da nossa página;
* margin: 0 auto: define uma margem 0px na vertical e automático na margem horizontal;

# Título Principal
No protótipo do Figma, o título está posicionado no canto esquerdo da tela. Para alcançar o mesmo resultado em nossa página, precisamos adicionar o seguinte código ao arquivo style.css

~~~css
.titulo-principal {
    text-align: left;
    width: 100%;
    font-size: 32px;
}
~~~
# O que esse código faz?
* Text-align: left: altera o texto para esquerda 
* Width:100%: define a largura da página em 100% 
* font-size: 32px: altera o tamanho da fonte

# Underline (traço baixo ou sublinhado)
Percebemos que no final do nosso título tem um _ (underline) na cor verde
![Como deve ficar](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula2_facacomoeufiz_img2.png)
Para mudar apenas a cor da linha:

* vá até a descrição do seu título no HTML
* envolva-o com a tag <span>.

~~~html
 <h2 class="titulo-principal">Meus Objetivos do ano<span>_</span></h2>
~~~

Volte ao arquivo CSS e aplique a classe título principal à tag <span>. Isso permitirá que apenas a cor do underline seja alterada.

~~~css
.titulo-principal span {
    color: var(--verde);
}

~~~
# Estilizando os botões
Agora vamos começar a estilizar nossos botões. Dentro da classe botao adicione o seguinte código:
~~~css
.botao {
    font-family: "Crakra Petch", sans-serif;
    background-color: var(--botao-inativo);
    color: var(--branco);
    display: flex;
    justify-content: center;
    padding: 1em;
    font-size: 18px;
    align-items: center;
    width: 100%;

~~~
# O que esse código faz?

font-family: altera a fonte do texto background-color: altera a cor de fundo para inativo color: altera a cor da fontes para branco display:flex, Justify-content:center: alinha e centraliza padding: adiciona espaçamento interno font-size: altera o tamanho da fonte align-items:center: alinha os botões width :100%: adiciona largura aos botões

Assim temos o seguinte resultado:



![img como fica](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula2_facacomoeufiz_img3.png)

# Estilizando as bordas
Observamos que as bordas ainda não estão iguais ao nosso protótipo. 
Para resolver isso, vamos ajustar o estilo das bordas dos nossos botões. 
Na mesma classe **botao**, adicione o seguinte código:
~~~css
    border-bottom: 4px solid var(--botao-ativo); 
    border-left: 2px solid var(--botao-ativo); 
    border-right: 2px solid var(--botao-ativo); 
    border-top: none;
~~~

# O que esse código faz?

* border-bottom: 4px solid var(--botao-ativo): na borda inferior adiciona uma espessura, formato e cor;
* border-left: 2px solid var(--botao-ativo): na borda esquerda adiciona uma espessura, formato e cor;
* border-right: 2px solid var(--botao-ativo): na borda direita adiciona uma espessura, formato e cor;
* border-top: none: remove a borda superior.
Assim temos o seguinte resultado:
![img como fica2](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula2_facacomoeufiz_img4.png)

Media Query e responsividade
Sabemos o quanto é importante que nossas páginas sejam responsivas, já que isso auxilia seu uso e visualização em diferentes telas. Vamos definir uma largura máxima, de 1200px, para nossa página. Isso significa que, quando a tela for mais larga do que isso, nosso conteúdo não se estenderá além dessa largura definida.

Para isso, faremos uso do recurso **media query**, que permite que o conteúdo se adapte a diferentes condições, como a resolução da tela.

Assim no nosso arquivo style.css vamos adicionar o seguinte código:
~~~css
.botoes {
    display: block;
}

@media screen and (min-width: 768px) {
    .botoes {
        display: flex;
    }
    }
~~~
Assim temos os seguinte resultado:

![Como deve ficar](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula02_facacomoeufiz_gif1.gif)


# Arredondamentos das bordas
Com base no nosso protótipo do Figma percebemos que as bordas dos cantos superiores são arredondadas, como mostra na imagem abaixo:
![botoes redondos](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula02_facacomoeufiiz_img5.png)
Para garantir que as bordas estejam arredondadas, tanto em telas maiores quanto em dispositivos menores, é necessário inserir o seguinte código **dentro do nosso media query**:

~~~css
.botao:first-child {
    border-radius: 40px 40px 0 0;

@media screen and (min-width: 768px) {
    .botoes {
        display: flex;
    }

    .botao:first-child {
        border-radius: 40px 0 0 0;
    }

    .botao:last-child {
        border-radius: 0 40px 0 0;
    }
}
~~~

O que esse código faz? Ele:

* .botao:first-child: seleciona somente o primeiro botão.
* botao:last-child: seleciona somente o último botão.
* border-radius: arredonda as bordas e cada valor se aplica a um canto específico no sentido horário, a partir do canto superior esquerdo.
Por enquanto esse é o resultado do nosso projeto:

![Como deve ficar](https://caelum-online-public.s3.amazonaws.com/3373-javascript/aula2_facacomoeufiz_gif2.gif)

## Como abrir o VScode Online 

Esse procedimento e para os computadores e notebook verdes .
obs: somente nos computadores e notebooks é posivel acompanhar como está ficando o site.
```sh
Acesse o link enviado
quando aberto aparecerá o icone do Vscode
clique e se pedir permição para abrir pode permitir 
irá abrir o vs code do computador com os codigos iniciais ou continuação
edite adicionando os novos codigos da aula e envie quando terminar
```

Esse procedimento é para os crhomebooks
obs: nos crhomebooks não é posivel acompanhar como está ficando o site,
soemnte editar os codigos.
```sh
Acesse o repositorio
apos aberto apert o ponto final do teclado 
. <- esse 
irá abrir o VScode.dev 
edite ou adicione e envie quando terminar
```

| Sites | Link |
| ------ | ------ |
| Alura | [Login alura][alura] |
| Vscode | [VsCode-Online][vscode] |
| Google Class | [ClassRoom][class] |


### Referências: 
[ALURA][alura]:  Projeto de vida: organizando objetivos futuros com matemática aplicada aula-02
## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [alura]: <https://www.alura.com.br/>
   [vscode]: <https://vscode.dev/>
   [class]: <https://classroom.google.com/>
   

![Alt Text](https://github.com/rischawarski/rischawarski/assets/38566736/972bc398-17ab-422b-a41c-98cf73e62ca6)
