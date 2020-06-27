float n4;
float n6;
char[] Chieft = {'C', 'h', 'i', 'e', 'f', '_', '_', '_', '_', '_', '_', 'T', 'h', 'o', 'm', 's', 'o', 'n'}; 
int textnumber;
int alpha;

import ddf.minim.*;
import ddf.minim.signals.*;
Minim minim;
AudioPlayer mySound;
 
void setup () {
  fullScreen(P3D);
  //size(1920,1080);
  noCursor();
  smooth();
  background (20);
  frameRate(24);
 
  minim = new Minim(this);
  mySound = minim.loadFile("mastering_break the habit-001.wav");    
  mySound.play();
  
}
 
void draw () {
  
  //saveFrame("output/BTH_#####.png");
  println(frameRate);
  
  fill(20,50);  
  noStroke();
  rect(0, 0, width, height);
  translate(width/2, height/2);
 
  for (int i = 0; i < mySound.bufferSize() - 1; i++) {
    textnumber = int(mySound.left.get(i)*21);
    if(textnumber>18) {
      textnumber=18;
    } else {
      textnumber = int(mySound.left.get(i)*21);
    }
    
    textSize(140);
    fill(41, 39, 36); //shadow
    text(Chieft,0,textnumber,-550,480,0);
    
    fill(0, 66, 105);
    text(Chieft,0,textnumber,-570,500,0);
 
    float angle = sin(i+n4)*10;
    float angle2 = 200+mySound.left.get(i);
    float angle3 = sin(i+n6)*10;
 
    float x = sin(radians(i))*(angle2+50);
    float y = cos(radians(i))*(angle2+250);
 
    float x3 = sin(radians(i))*(100/angle)*(mySound.left.get(i)*10);
    float y3 = cos(radians(i))*(100/angle3)*(mySound.right.get(i)*100);
    
    textSize(25);
    fill(163,0,155);
    text("Break the habit (Original Mix)",x3-2300,y3-650);
    
    alpha = int(mySound.right.get(i)*200);
    if(alpha>255) {
      alpha=255;
    } else {
      alpha = int(mySound.left.get(i)*200);
    }    
    
    fill ( #999999, alpha/2); //grey
    ellipse(y3, x3, mySound.left.get(i)*angle2, mySound.right.get(i)*angle3);
 
    fill (#000000, 90); //black
    ellipse(x, y, mySound.left.get(i)*80, mySound.right.get(i)*40);
 
    fill ( #ffffff, alpha); //white
    ellipse(x3, y3, mySound.left.get(i)*angle*10, mySound.right.get(i)*angle3);
 
    fill ( #a3009b  , 199); //pink
    rect(x, y, mySound.right.get(i)*20, mySound.left.get(i)*20);
   
    fill( #004269 , 255); //blue
    ellipse(y, x, mySound.left.get(i)*angle, mySound.right.get(i)*angle2);
  }
 
  n4 += 0.018;
  n6 += 0.34;
 
}
