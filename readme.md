# Jogo da cobrinha 

O *jogo da cobrinha* tem como objetivo mover a cobra em direção à maçã. O jogo começa com uma cobra de tamanho 5 células, posicionada em um plano de 20x20, que busca a sua maçã que ocupa apenas 1 célula.

# Tecnologias utilizadas
1. **HTML**: é uma linguagem de marcação utilizada na construção de estruturas de páginas na Web.
2. **CSS**: Cascading Style Sheets (CSS) é um mecanismo para adicionar estilos (cores, fontes, espaçamento, etc.) a um documento Web.

# Funções principais
Apresentação e definição das duas funções principais do site:

### Game
Esta função apresenta o funcionamento do jogo como um todo, configurando a posição e movimento da cobra e a parte gráfica do jogo, isto é, definindo a cor do palco, da cobra e da maçã.
```
         function game() {
                px += vx;
                py += vy;
                if (px <0){
                    px = qp-1;
                }
                if (px > qp-1){
                    px = 0;
                }
                if (py <0){
                    py = qp-1;
                }
                if (py > qp-1){
                    py = 0;
                }

            ctx.fillStyle = "black";
            ctx.fillRect(0,0, stage.width, stage.height); 

            ctx.fillStyle= "red";
            ctx.fillRect(ax*tp, ay*tp, tp,tp);

            ctx.fillStyle = "gray";
            for (var i = 0; i < trail.length; i ++){
                ctx.fillRect(trail[i].x*tp, trail[i].y*tp, tp-1,tp-1);
                if (trail[i].x == px && trail[i].y == py)
                {
                    vx = vy = 0;
                    tail = 5;
                }
            }
            
        trail.push({x:px, y:py})
        while (trail.length > tail) {
            trail.shift();
        }
        if (ax==px && ay==py){
            tail++;
            ax = Math.floor(Math.random()*qp);
            ay = Math.floor(Math.random()*qp);
        }
    }
```
### keyPush
Esta função está diretamente relacionada ao posicionamento da cobra, verificando qual tecla está sendo pressionada para a cobra seguir a direção dada.
```
    function keyPush(event){
            switch (event.keyCode) {
                case 37: // left
                    vx = -vel;
                    vy = 0;
                    break;
                case 38: // up
                    vx = 0;
                    vy = -vel;
                    break;
                case 39: // right
                    vx = vel;
                    vy = 0;
                    break;
                case 40: // down
                    vx = 0;
                    vy = vel;
                    break;          
                default:
         
            break;
        }
    }
```

## Como rodar o código

>Baixe o código e abra o arquivo **_index.html_** no seu navegador.

## Imagem da tela
tela 1: tela de abertura
![](/imagens/tela1.png)

tela 2: início do jogo
![](/imagens/tela2.png)

#### Referências

* HTML: [YouTube](https://www.youtube.com/watch?v=Hua1OSXitdQ)