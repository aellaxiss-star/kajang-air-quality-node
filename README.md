kajang-air-quality-node
A lightweight IoT air quality monitoring node built on the ESP32-S3. Streams real-time PM2.5, CO levels, temperature, and humidity to a static web dashboard over local REST API polling with fallback simulation.

Overview
1. Firmware: ESP32-S3 running an asynchronous web server that exposes sensor data at the /data endpoint.
2. Frontend: Single-page web dashboard built with HTML5 and Vanilla JS. It periodically fetches telemetry data and supports CORS.
3. Dual Mode: Supports both live hardware connection via local IP and an off-grid simulation mode for testing.

Hardware Connections
- PMS5003 (PM2.5 Sensor): Connects via UART2 (TX to GPIO 17, RX to GPIO 18) at 9600 baud.
- MQ-7 (Carbon Monoxide Sensor): Connects via Analog pin (AO to GPIO 4).
- DHT22 (Temperature & Humidity Sensor): Connects via Digital pin (Data to GPIO 15 with a 10k pull-up resistor).

Telemetry Data Format
The ESP32 returns data in JSON format from the /data endpoint:
- Node Name: Kajang-Air-01
- PM2.5: Numerical reading in ug/m3
- CO Raw: Raw analog reading
- Temperature: Reading in degrees Celsius
- Humidity: Percentage reading

Quick Start
1. Download or clone this repository.
2. Open index.html directly in a browser or access it via GitHub Pages.
3. Use Simulation Mode, or enter your ESP32 board's local IP address to stream live data.
