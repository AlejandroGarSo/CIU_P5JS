# CIU_P5JS
Por Alejandro García Sosa

## Descripción del proyecto:
En esta octava práctica, hemos trabajado con p5.js. El objetivo era realizar un sketch de máximo 1024 caracteres, el cual será evaluado por los compañeros de la asignatura. El sketch diseñado genera círculos que van ocupando la pantalla, 


## Diseño:
El código genera un punto y 2 colores aleatorios, los cuales servirán como punto central del círculo, así como el color de fondo y del círculo. Cuando el círculo ocupa toda la pantalla, el color del círculo se convierte en el color del fondo, y genera otro punto y otro color de relleno aleatorio.
Para calcular si el círculo ocupa toda la pantalla, comparamos compara las componentes rojas de las esquinas opuestas, y luego una de ellas con al componente roja del color del círculo.
```
get(0,0)[0] == get(width-1,height-1)[0] && get(width-1,0)[0] == get(0,height-1)[0] && get(0,0)[0] == round(red(spcol))
```
Para facilitar la lectura del código, ya que está escrito de forma que ocupe el menor número de caracteres posible, el siguiente código está en un formato más legible.
```
var bgcol, spcol, x=0, y=0, size=10;
function setup(){
  createCanvas(400,400);
  bgcol=color(random(255),random(255),random(255));
  spcol=color(random(255),random(255),random(255));
}
function draw(){
  background(bgcol);
  strokeWeight(5);
  stroke(0);
  fill(spcol);
  circle(x,y,size);
  size+=5;
  if(get(0,0)[0] == get(width-1,height-1)[0] && get(width-1,0)[0] == get(0,height-1)[0] && get(0,0)[0] == round(red(spcol))){
    size=10;
    x=random(width-1);
    y=random(height-1);
    bgcol=spcol;
    spcol=color(random(255),random(255),random(255));
  }
}
```
## Bibliografía:
- Diapositivas de la asignatura de CIU.
- Guion de prácticas de la asignatura de CIU.
- https://www.openprocessing.org/
- https://p5js.org/es/reference/
