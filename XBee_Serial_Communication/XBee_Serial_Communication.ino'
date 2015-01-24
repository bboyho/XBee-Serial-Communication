/*
Wireless XBee Series 1 Serial Communication
By Ho Yun Bobby Chan @ SparkFun Electronics

This is example code used to wirelessly transmit characters
through an Arduino's software serial UART pins to another Arduino
using two XBee Series 1 in the same channel. For more information 
on configuring two XBee Series 1 on the same channel, you can check
out Digi's Examples:
http://examples.digi.com/get-started/basic-xbee-802-15-4-chat/
*/

#include <SoftwareSerial.h>
SoftwareSerial xbee(2,3); //RX, TX
char val;

void setup(){
  Serial.begin(9600); 
  Serial.println( "Arduino started sending bytes via XBee" );

  xbee.begin(9600);
  //xbee.println("Hello world");
}

void loop(){
  /*if (Serial.available()){
    Serial.println(Serial.read()); 
    //send character through Software Serial to XBee
    //should receive on other XBee connected to Tera Term
  }*/
  xbee.write("A");
  delay(500);
  
  //if xbee is receiving data from another XBee
  if (xbee.available())
  //write what was received on the Serial Monitor
    Serial.write(xbee.read());
    
   //if you are transmitting data to the other Xbee
  if (Serial.available())
  //send data from the Serial Monitor to the other Xbee
    xbee.write(Serial.read());

}
