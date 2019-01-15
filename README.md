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

### Ejemplo 07

```processing
PImage img;

void setup(){  
  size (800,600);
  background(180);
  img = loadImage("pony.png");
}

void draw(){
  background(180);
  image(img,0,0);
  ellipse(mouseX,mouseY,50,50); 
}
```


### Ejemplo 99

```processing
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

```processing
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
  for (Particle p : particles)p.run();
}


void mousePressed()
{
  background(255);
  init();
}
```

## Referencias

- [Video introductorio, en inglés](https://www.pbs.org/video/-book-art-creative-coding/)
- [Processing](https://processing.org/)
- [Editor on-line](https://www.openprocessing.org/sketch/create)
- [Videotutorial básico de Processing con Daniel Shiffman, en inglés](https://hello.processing.org/editor/)
- [Un listado muy extenso de recursos. Creative Coding Awesone](https://github.com/terkelg/awesome-creative-coding)
