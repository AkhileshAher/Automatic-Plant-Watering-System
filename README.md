# Automatic Plant Watering System

## Project Overview

The **Automatic Plant Watering System** is an IoT-based project that utilizes an Arduino to monitor the moisture level of the soil and control a water pump for efficient plant irrigation. The system reads data from a soil moisture sensor and automatically waters the plant when the soil becomes dry, ensuring that the plant receives the right amount of water without requiring manual intervention.

This project uses an Arduino microcontroller and a relay module to control the water pump based on the moisture level from the sensor.

## Components Used

- **Arduino Uno** (or any compatible Arduino board)
- **Relay Module** (for controlling the water pump)
- **Soil Moisture Sensor** (to detect the moisture level of the soil)
- **Water Pump** (to water the plant)
- **Jumper wires** and **breadboard** (for connections)

## Circuit Diagram

1. **Soil Moisture Sensor**: Connect the signal pin of the soil moisture sensor to **pin 6** of the Arduino.
2. **Relay Module**: Connect the input pin of the relay module to **pin 3** of the Arduino.
3. **Water Pump**: Connect the water pump to the relay's output terminals to control the power supply to the pump.

## Arduino Code

```cpp
int water; // Variable to store soil moisture status

void setup() {
  pinMode(3, OUTPUT);  // Output pin for relay to control water pump
  pinMode(6, INPUT);   // Input pin to read signal from soil moisture sensor
}

void loop() {
  water = digitalRead(6);  // Read the signal from the soil moisture sensor

  if(water == HIGH) {  // If the soil is moist (sensor reads HIGH), stop watering
    digitalWrite(3, LOW);  // Turn off the relay to stop water supply
  } else {  // If the soil is dry (sensor reads LOW), turn on the pump
    digitalWrite(3, HIGH);  // Turn on the relay to supply water
  }

  delay(400);  // Delay for stability
}
```

## How It Works

1. The soil moisture sensor continuously monitors the moisture level of the soil.
2. When the soil is sufficiently moist, the sensor sends a signal (HIGH) to the Arduino, and the Arduino cuts off the water supply by deactivating the relay.
3. When the soil is dry, the sensor sends a LOW signal to the Arduino, which turns on the relay, activating the water pump to water the plant.
4. The process repeats in a loop, ensuring that the plant is always watered when necessary.

## Features

- **Automatic watering**: No manual intervention required; the system waters the plant automatically when the soil becomes dry.
- **Soil moisture sensing**: Continuously monitors the moisture level to ensure optimal watering.
- **Energy-efficient**: Watering only happens when required, saving both water and energy.

## Installation & Setup

1. **Connect the hardware**: Wire the soil moisture sensor, relay module, and water pump according to the circuit diagram above.
2. **Upload the code**: Open the Arduino IDE, paste the code, and upload it to the Arduino board.
3. **Power the system**: Provide power to the Arduino and the water pump (through the relay).

## Troubleshooting

- **Water pump doesn't turn on**: Check the connections between the relay module and the pump. Ensure the relay is receiving power and is properly connected to the Arduino.
- **Soil moisture sensor not working**: Make sure the sensor is correctly connected to pin 6 of the Arduino. Ensure that the sensor is properly inserted in the soil.

## Conclusion

This automatic plant watering system is a simple and effective way to automate the process of watering plants, ensuring they are well-maintained without human intervention. This project is ideal for beginners in Arduino, providing a hands-on approach to learning about sensors, relays, and automation systems.

