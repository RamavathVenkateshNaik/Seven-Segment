//----------------------Skeleton Code--------------------//
#include <WiFi.h>
#include <WiFiUdp.h>
#include <ArduinoOTA.h>

//    Can be client or even host   //
#ifndef STASSID
#define STASSID "1234"  // Replace with your network credentials
#define STAPSK  "7601048418"
#endif

const char* ssid = STASSID;
const char* password = STAPSK;


void OTAsetup() {
  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);
  while (WiFi.waitForConnectResult() != WL_CONNECTED) {
    delay(1000);
    ESP.restart();
  }
  ArduinoOTA.begin();
}

void OTAloop() {
  ArduinoOTA.handle();
}

//-------------------------------------------------------//

// Define pin for the single LED
const int ledPin = 2; // Choose any digital pin for the LED

// Define the states
enum State {S0, S1, S2, S3, S4};
State currentState = S0;

void setup() {
	OTAsetup();
  pinMode(ledPin, OUTPUT); // Initialize LED pin as output
}

void loop() {
	OTAloop();
  // Determine if LED should be ON or OFF based on current state
  int ledState = currentState % 2; // Alternates between 0 (OFF) and 1 (ON)

  // Set LED state
  digitalWrite(ledPin, ledState);

  // Perform state transition based on the sequence "01010"
  switch (currentState) {
    case S0:
      currentState = S1;
      break;
    case S1:
      currentState = S2;
      break;
    case S2:
      currentState = S3;
      break;
    case S3:
      currentState = S4;
      break;
    case S4:
      currentState = S0;
      break;
  }

  delay(1000); // Delay for 1 second before transitioning to the next state
}
