# CreativeCoding
Programación Creativa


## Funciones básicas

### Lienzo

```processing
size(w,h);
```
---

```
0,0-------> hacia infinito positivo
 |
 |
 v
hacia infinito positivo
```

### Figuras

```processing
rect(x,y,w,h)
ellipse(x,y,w,h)
```
---

``` 
- x - coordenada x
- y - coordenada y
- w (width)  - ancho
- h (height) - alto
``` 




### Fondo, color de línea y de relleno

```processing
background(r,g,b);
stroke(r,g,b);
fill(r,g,b);
```
---

``` 
- r (red)   - cantidad de rojo, de 0 (ninguno) a 255 (máximo)
- g (blue)  - cantidad de verde, de 0 (ninguno) a 255 (máximo)
- b (green) - cantidad de azul, de 0 (ninguno) a 255 (máximo)
```


### Ejemplo 01 

```processing
void setup() {
  size(500,400);
}

void draw() {
  background(0);

  stroke(255);
  fill(128);
  ellipse(mouseX, mouseY, 100, 100);
}
```

### Ejemplo 02

```processing
void setup() {
  size(500,400);
  background(0);
}

void draw() {
  stroke(255);
  fill(128);
  ellipse(mouseX, mouseY, 100, 100);
}
```

### Ejemplo 03

```processing
void setup() {
  size(500, 400);
  background(10, 80, 100);
}

void draw() {
  stroke(255, 255, 255);
  fill(160, 220, 90);
  ellipse(mouseX, 200, 300, 300);

  fill(160, 210, 230);
  rect(245, mouseY, 10, 240);

  fill(255, 255, 255);
  ellipse(mouseX, mouseY, 70, 70);
}
```

### Ejemplo 04

```processing
void setup() {
  size(500,400);
}

void draw() {
  background(0);

  stroke(255);
  fill(128);
  ellipse(250, 200, 100, 100);

  if (mousePressed) {
    rect(250,200,100,100);
  }
}
```

### Ejemplo 05

```processing
void setup() {
  size(500,400);
}

void draw() {
  background(0);
  stroke(255);
  fill(128);

  if (mousePressed) {
    rect(250,200,100,100);
  } else {
    ellipse(250, 200, 100, 100);
  }
}
```

### Ejemplo 06

```processing
void setup() {
  size(500, 400);
  background(10, 80, 100);
}

void draw() {
  if (mousePressed) {
    background(10, 80, 100);
  } 

  stroke(255, 255, 255);
  fill(160, 220, 90);
  ellipse(mouseX, 200, 300, 300);

  fill(160, 210, 230);
  rect(245, mouseY, 10, 240);

  fill(255, 255, 255);
  ellipse(mouseX, mouseY, 70, 70);
}
```

## Referencias

- [Video introductorio, en inglés](https://www.pbs.org/video/-book-art-creative-coding/)
- [Processing](https://processing.org/)
- [Editor on-line](https://www.openprocessing.org/sketch/create)
- [Videotutorial básico de Processing con Daniel Shiffman, en inglés](https://hello.processing.org/editor/)
- [Un listado muy extenso de recursos. Creative Coding Awesone](https://github.com/terkelg/awesome-creative-coding)
