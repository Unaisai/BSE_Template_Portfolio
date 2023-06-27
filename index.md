# Bluestamp wandering table-top Rover
During this project, I built a rover in which has the ability to wander on its own and avoid obsticales such as the edge of table tops. Using the Arduino Uno, which is a programable board that sends signals via digital pins. I coded the rover to acknowledge the obstacles and then perform a series of movements in order to avoid the obstacles. This project made me become extremely focussed on the technicallities of what makes a rover function. This includes both hardware and wiring, and code.
| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Unai C. Z. | Fiorello H. Laguardia HS | Electrical Engineering | Incoming Senior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](IMG_2748.JPG)
  
# Final Milestone
For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Second Milestone
During my second Milestone, I had some drawbacks of motors not working and then revisting and revising my code in order to get the correct functionality out of my code. I eventually got the Rover to work correctly after switching the electrical pins on the arduino and rewriting to the code to match exactly what I had rewired on the Arduino. This lead me to be able to write code in order for my rover to recognize the edge of a table using a digital signal sent from the IR sensors, and then react by backing up and turning around. This was a huge step during the project, because recognizing the edge of a table is the first step when making a rover that can avoid certain obstacles. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IWtPTOME1gg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# First Milestone
During my first Milestone, I started by putting together the parts so that they can be in places that had utility for later code and programs.
In order to test the hardware, I used a test program to run the motors in all directions to make sure that everything is hooked up correctly. however I began to have some issues when the motors didn't work in unisen. While troubleshooting,iI learned how to hot wire my rover in order to isolate the problem. I started by manually putting the rover into forward and backward

<iframe width="560" height="315" src="https://www.youtube.com/embed/GgeViYFkuSQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here is the code, using Rasberry pi, I coded a program in which the rover uses IR sensors to recognize the edge of a surface, and then respond by backing away.
```c++
const int in1 = 3;
const int in2 = 4;
const int in3 = 11;
const int in4 = 12;
const int ir = 2;
const int rightIR = 6;
const int leftIR = 7;

void setup(){
  pinMode(3, OUTPUT); // 3 and 4: right motor
  pinMode(4, OUTPUT);
  pinMode(11, OUTPUT); // 11 and 12: left motor
  pinMode(12, OUTPUT);
	pinMode(2, INPUT); // ir sensor
  pinMode(6, INPUT); // right IR
  pinMode(7, INPUT); // left IR
	pinMode(13, OUTPUT); // status led
  

Serial.begin(9600);
}

void loop(){
	int sensorValue = digitalRead(2);
  int RsensorValue = digitalRead(6);
  int LsensorValue = digitalRead(7);

Serial.println(RsensorValue);
if (sensorValue == 1){
//off the table
  digitalWrite (13, LOW);
}
if (sensorValue == 0) {
	//on the table 
	digitalWrite (13 , HIGH);
}
while (sensorValue == 1)
{
  moveBackward();
  if (RsensorValue);
  stopMove();
  delay(500);
  if (LsensorValue);
  stopMove();
  delay(500);
}
while (RsensorValue == 1)
{
  moveForward();
  delay(400);
  stopMove();
  delay(200);
}
while (LsensorValue == 1)
  moveForward();
  delay(400);
loop();
 if (sensorValue == 1)
  stopMove();
  delay(200);
}

void moveBackward() {
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH);
}

void stopMove() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, LOW);
}

void turnLeft() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH);
}

void moveForward()  {
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);
}

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
|:--:|:--:|:--:|:--:|

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
