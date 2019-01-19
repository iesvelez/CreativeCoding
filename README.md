# CreativeCoding

Programación Creativa


## Introducción

Esto es una iniciación a la Programación Creativa usando el lenguaje Processing, el cual se basa en Java.

El enlace para descargar el entorno de desarrollo es el siguiente:

- [Descarga de Processing](https://processing.org/download/)


## Características del lenguaje

### Estructura del programa

```processing

void setup () {
  // Función de inicialización
}

void draw () {
  // Función de dibujo. Se está ejecutando continuamente, una y otra vez de forma infinita
}
```

### Lienzo

```processing
size (w,h);
```
---

### Coordenadas del lienzo

![coordenadas de pantalla](images/coordenadas.svg)



### Figuras

```processing
point   (x, y);
line    (x1, y1, x2, y2);
rect    (x, y, w, h)
ellipse (x, y, w, h)
```
---

``` 
- x - coordenada x
- y - coordenada y
- w (width)  - ancho
- h (height) - alto
``` 

### Ejemplo 01 

```processing
void setup () {
  size (600,400);
}


void draw () {
   ellipse (300, 200, 50, 50);
}
```


### Fondo, color de línea y de relleno

Para indicar la intensidad de color se utiliza el intervalo numérico **de 0 a 255**, siendo:

```
- 0        ausencia de color.
  .
  .        distintos grados de color.
  .
- 255      color intenso.
``` 

#### Blanco

En la mayoría de las pantallas, la ausencia de color se interpreta como negro.

Si trabajamos únicamente con escalas de grises, a medida que añadimos "color" la imagen se va haciendo cada vez más blanca.
 

```processing
background (w);  // Fondo
stroke     (w);  // Color de línea de las figuras
fill       (w);  // Color de relleno de las figuras
```

```
- w (white)   - cantidad de blanco,  de 0 (ninguno) a 255 (máximo)
```

![escala grises](images/gris.png)


#### Colores

```processing
background (r,g,b);  // Fondo
stroke     (r,g,b);  // Color de línea de las figuras
fill       (r,g,b);  // Color de relleno de las figuras
```

``` 
- r (red)   - cantidad de rojo,  de 0 (ninguno) a 255 (máximo)
- g (blue)  - cantidad de verde, de 0 (ninguno) a 255 (máximo)
- b (green) - cantidad de azul,  de 0 (ninguno) a 255 (máximo)
```

![escala RGB](images/rgb.png)


Combinando los distintos colores, en distinto grado, podemos obtener todo el resto de colores.


![colores RGB](images/colores.jpg)


#### Opacidad

Es el grado en el cual un color deja pasar la luz, es decir su opacidad/transparencia.

```processing
background (r,g,b,a);  // Fondo
stroke     (r,g,b,a);  // Color de línea de las figuras
fill       (r,g,b,a);  // Color de relleno de las figuras
```

El cuarto parámetro se conoce como **alfa**, e indica el grado de opacidad.

```
- a (alpha)   - grado de opacidad,  de 0 (transparente) a 255 (opaco)
```

![escala opacidad](images/opacidad.png)




### Ejemplo 02

```processing
// COLORES

void setup () {
  size (600,200);
}


void draw () {
   fill (255, 0, 0); // ROJO BRILLANTE
   ellipse (50, 50, 40, 40);
   fill (0, 255, 0); // VERDE BRILLANTE
   ellipse (150, 50, 40, 40);
   fill (0, 0, 255); // AZUL BRILLANTE
   ellipse (250, 50, 40, 40);

   fill (255, 255, 0); // ROJO BRILLANTE + VERDE BRILLANTE
   ellipse (350, 50, 40, 40);
   fill (0, 255, 255); // VERDE BRILLANTE + AZUL BRILLANTE
   ellipse (450, 50, 40, 40);
   fill (255, 0, 255); // ROJO BRILLANTE + AZUL BRILLANTE
   ellipse (550, 50, 40, 40); 
   
   fill (128, 0, 0); // ROJO MEDIO
   ellipse (50, 150, 40, 40);
   fill (0, 128, 0); // VERDE MEDIO
   ellipse (150, 150, 40, 40);
   fill (0, 0, 128); // AZUL MEDIO
   ellipse (250, 150, 40, 40);
   
   fill (255, 255, 255); // ROJO BRILLANTE + VERDE BRILLANTE + AZUL BRILLANTE = BLANCO
   ellipse (350, 150, 40, 40);
   fill (0, 0, 0);      // NINGUN COLOR = NEGRO
   ellipse (450, 150, 40, 40);   
   fill (128, 128, 128); // GRIS
   ellipse (550, 150, 40, 40); 
}
```

### Ejemplo

```processing
// POSICIONES ALEATORIAS

void setup () {
  size (600,420);
  background(128);
}

void draw () {
   ellipse( random(0,width), random(0,height), 20, 20); 
}
```

### Ejemplo 

```processing
// POSICIONES Y COLORES ALEATORIOS

void setup () {
  size (600,420);
  background(255);
}


void draw () {
   fill ( random(0,255), random(0,255), random(0,255), random(0,255) );
   ellipse( random(0,width), random(0,height), 20, 20); 
}
```

### Ejemplo 

```processing
// POSICIONES, COLORES Y TAMAÑOS ALEATORIOS
float radio;

void setup () {
  size (600,420);
  background(255);
}


void draw () {
   fill ( random(0,255), random(0,255), random(0,255), random(0,255) );
   radio = random (10, 50);
   ellipse( random(0,width), random(0,height), radio, radio); 
}
```


### Ejemplo

```processing
// POSICIONAMIENTO CON EL RATÓN

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

### Ejemplo

```processing
// POSICIONAMIENTO CON EL RATÓN

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

### Ejemplo

```processing
// OPACIDAD
//   0: totalmente transparente
// 255: totalmente opaco

void setup() {
  size(600,400); 
  noStroke();
  background(0);  
}

void draw() {
  fill(128, 20);  // Relleno color gris (128), opacidad: 20 (en rango 0 a 255)
  ellipse(mouseX, mouseY, 30, 30);
}
```

### Ejemplo

```processing
// OPACIDAD
//   0: totalmente transparente
// 255: totalmente opaco

void setup() {
  size(600,400); 
  noStroke();
  background(0);  
}

void draw() {
  fill(0, 20);  // Relleno color negro (0), opacidad: 20 (en rango 0 a 255)
  rect(0,0,width,height);

  fill (255);
  ellipse(mouseX, mouseY, 30, 30);
}
```


### Ejemplo 

```processing
// PELOTA MOVIENDOSE

int posX = 0;
int posY = 0;

void setup () {
  size (600,400);
  background(128);
  stroke(255,0,0);
  fill(255);
  ellipse(posX, posY, 20, 20);
}

void draw () {
   posX = posX + 2;
   posY = posY + 2;
   
   background(128);
   ellipse(posX, posY, 20, 20); 
}
```

### Ejemplo 

```processing
// PELOTA REBOTANDO

int posX = 0;
int posY = 0;

int incX = 2;
int incY = 2;

void setup () {
  size (600,420);
  background(128);
  stroke(255,0,0);
  fill(255);
  ellipse(posX, posY, 20, 20);
}

void draw () {
   // background (128);
   posX = posX + incX;
   posY = posY + incY;
   
   if (posX > width  || posX < 0) incX = -incX; // Cambiamos de dirección en X
   if (posY > height || posY < 0) incY = -incY; // Cambiamos de dirección en Y
  
   ellipse(posX, posY, 20, 20); 
}
```


### Ejemplo 

```processing
// VARIAS FIGURAS

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


### Ejemplo 

Para el siguiente ejemplo es necesaria la siguiente imagen:

![pony](pony.png)

```processing
// IMAGEN COMO FONDO
// El tamaño indicado en size() debe ser exactamente igual al de la imagen.

PImage img;

void setup(){  
  size (600,423); // Tamaño de la imagen "pony.png"
  img = loadImage("pony.png");
  background(img);
}

void draw(){
  background(img);
  ellipse(mouseX,mouseY,50,50); 
}
```

### Ejemplo 

```processing
// EVENTOS DEL RATÓN

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


### Ejemplo 

```processing
// FUNCION EXIT

void setup() {
  size(500,400);
}

void draw() {
  line(mouseX, mouseY, width/2, height/2);
}

void mousePressed() {
  exit(); 
}
``` 


### Ejemplo 

```processing
// EVENTOS DEL RATÓN

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

### Ejemplo 

```processing
// EVENTOS DEL RATÓN

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


### Ejemplo 

Para el siguiente ejemplo es necesaria la siguiente imagen:

![mario](mario.png)

```processing
// EVENTOS DEL TECLADO

int posX; 
int posY;
PImage img;


void setup(){
  size(800,600);
  img = loadImage("mario.png");
  posX = width/3;
  posY = height/3;  
}


void draw(){
  background(180);
  image(img, posX, posY);
}


void keyPressed()
{

  switch (keyCode) {
    case UP:     posY -= 10; break;
    case DOWN:   posY += 10; break;
    case LEFT:   posX -= 10; break;
    case RIGHT:  posX += 10; break;
    default:
  }
  
  switch (key) {
    case '0':    posX =   0; break;
    case '1':    posX = 100; break;
    case '2':    posX = 200; break;
    case 'A':
    case 'a':    posY =   0; break;
    case 'B':   
    case 'b':    posY = 100; break;
    case 'C':   
    case 'c':    posY = 200; break;
    case ENTER:
    case RETURN: posX = width/3; posY = height/3; break;
    case ESC:    exit();
    default:    
  } 
}

void mousePressed()
{
  exit();
} 
```


### Ejemplo 98

```processing
// PELOTAS REBOTANDO

int numBalls = 12;
float spring = 0.05;
float gravity = 0.03;
float friction = -0.9;
Ball[] balls = new Ball[numBalls];

void setup() {
  size(640, 360);
  for (int i = 0; i < numBalls; i++) {
    balls[i] = new Ball(random(width), random(height), random(30, 70), i, balls);
  }
  noStroke();
  fill(255, 204);
}

void draw() {
  background(0);
  for (Ball ball : balls) {
    ball.collide();
    ball.move();
    ball.display();  
  }
}

class Ball {
  
  float x, y;
  float diameter;
  float vx = 0;
  float vy = 0;
  int id;
  Ball[] others;
 
  Ball(float xin, float yin, float din, int idin, Ball[] oin) {
    x = xin;
    y = yin;
    diameter = din;
    id = idin;
    others = oin;
  } 
  
  void collide() {
    for (int i = id + 1; i < numBalls; i++) {
      float dx = others[i].x - x;
      float dy = others[i].y - y;
      float distance = sqrt(dx*dx + dy*dy);
      float minDist = others[i].diameter/2 + diameter/2;
      if (distance < minDist) { 
        float angle = atan2(dy, dx);
        float targetX = x + cos(angle) * minDist;
        float targetY = y + sin(angle) * minDist;
        float ax = (targetX - others[i].x) * spring;
        float ay = (targetY - others[i].y) * spring;
        vx -= ax;
        vy -= ay;
        others[i].vx += ax;
        others[i].vy += ay;
      }
    }   
  }
  
  void move() {
    vy += gravity;
    x += vx;
    y += vy;
    if (x + diameter/2 > width) {
      x = width - diameter/2;
      vx *= friction; 
    }
    else if (x - diameter/2 < 0) {
      x = diameter/2;
      vx *= friction;
    }
    if (y + diameter/2 > height) {
      y = height - diameter/2;
      vy *= friction; 
    } 
    else if (y - diameter/2 < 0) {
      y = diameter/2;
      vy *= friction;
    }
  }
  
  void display() {
    ellipse(x, y, diameter, diameter);
  }
}
```

### Ejemplo 99

```processing
// PARTICULAS


float xoff, yoff, zoff, inc, col;
int rez, cols, rows, num;
PVector[] vectors;
ArrayList<Particle> particles;

void setup() {
  size(700, 500);
  colorMode(HSB);
  init();
}


void init() {
  background(0);
  rez = 10;
  inc = 0.1;
  num = 1000;
  col = random(255);
  cols = floor(width / rez) + 1;
  rows = floor(height / rez) + 1;
  vectors = new PVector[cols * rows];
  particles = new ArrayList<Particle>();
  for (int i=0; i<num; i++)
    particles.add(new Particle());
}

void draw() {
  yoff = 0;
  for (int y=0; y<rows; y++) {
    xoff = 0;
    for (int x=0; x<cols; x++) {
      float angle = noise(xoff, yoff, zoff) * TWO_PI * 2;
      PVector v = PVector.fromAngle(angle);
      v.setMag(1);
      vectors[x + y * cols] = v;
      xoff += inc;
    }
    yoff += inc;
  }
  zoff += 0.005;
  if (col < 255)col += 0.1;
  else col = 0;
  for (Particle p : particles) p.run();
}

void mousePressed()
{
  background(255);
  init();
}



class Particle {
  PVector pos, vel, acc, prev;
  float max = random(2, 8);
  
  Particle() {
    pos = new PVector(width/2, height/2);
    prev = new PVector(pos.x, pos.y);
    vel = new PVector(0, 0);
    acc = new PVector(0, 0);
  }
  
  void copy() {
    prev.x = pos.x;
    prev.y = pos.y;
  }
  
  void run() {
    follow();
    update();
    show();
  }
  
  void update() {
    pos.add(vel);
    vel.limit(max);
    vel.add(acc);
    acc.mult(0);
    if (pos.x > width) {
      pos.x = 0; 
      copy();
    }  
    if (pos.x < 0) {
      pos.x = width; 
      copy();
    } 
    if (pos.y > height) {
      pos.y = 0; 
      copy();
    }  
    if (pos.y < 0) {
      pos.y = height; 
      copy();
    }
  }
  
  void follow() {
    int x = floor(pos.x / rez);
    int y = floor(pos.y / rez);
    PVector force = vectors[x + y * cols];
    acc.add(force);
  }
  
  void show() {
    stroke(col, 255, 255, 5);
    line(pos.x, pos.y, prev.x, prev.y);
    copy();
  }
}
```


## Referencias

- [Video introductorio, en inglés](https://www.pbs.org/video/-book-art-creative-coding/)
- [Processing](https://processing.org/)
- [Videotutorial básico de Processing con Daniel Shiffman, en inglés](https://hello.processing.org/editor/)
- [Un listado muy extenso de recursos. Creative Coding Awesone](https://github.com/terkelg/awesome-creative-coding)
