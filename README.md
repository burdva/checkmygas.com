# Check My Gas (checkmygas.com)

**Open-source web interface for the Burdva GM-1000 LPG Level Monitor.**

CheckMyGas is an independent, browser-based application that connects to the **Burdva GM-1000** device over **Bluetooth Low Energy (BLE)** to monitor LPG cylinder levels and related device data.

The goal is simple: provide users with an accessible web interface for interacting with their LPG monitoring hardware without requiring a dedicated native application.

## What is the Burdva GM-1000?

The **Burdva GM-1000** is an LPG level monitoring device designed to help users track the amount of LPG remaining in a cylinder.

The device communicates wirelessly using **Bluetooth Low Energy (BLE)**, allowing compatible devices such as smartphones and computers to connect directly to it.

## CheckMyGas

CheckMyGas provides a web-based interface for communicating with the GM-1000.

The application uses the browser's **Web Bluetooth API** to establish a BLE connection with compatible GM-1000 devices.

### Core capabilities

* Connect to the Burdva GM-1000 over BLE
* Read LPG level information from the device
* Display LPG level data through a web interface
* Communicate directly with the hardware from a compatible browser
* No dedicated mobile application required
* Open-source and independently accessible

## How It Works

The basic communication flow is:

```text
┌─────────────────────┐
│   Burdva GM-1000    │
│   LPG Level Sensor  │
└──────────┬──────────┘
           │
           │ Bluetooth Low Energy
           ▼
┌─────────────────────┐
│   Web Bluetooth API │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│    CheckMyGas Web   │
│     Application     │
└─────────────────────┘
```

The browser establishes a BLE connection to the GM-1000 and communicates with the device using its supported BLE services and characteristics.

## Browser Compatibility

CheckMyGas relies on the **Web Bluetooth API**.

Browser and operating-system support for Web Bluetooth varies. A compatible browser and Bluetooth-enabled device are required.

For the best experience, use a browser that supports Web Bluetooth and ensure Bluetooth is enabled on your device.

## Getting Started

Open the CheckMyGas web application in a compatible browser.

1. Enable Bluetooth on your device.
2. Open CheckMyGas.
3. Select the option to connect to a GM-1000.
4. Select the available Burdva GM-1000 device.
5. Approve the Bluetooth connection.
6. View the LPG level information provided by the device.

No account or cloud connection is required for the basic BLE communication flow.

## Open Source

CheckMyGas is an open-source project intended to make interaction with the Burdva GM-1000 more accessible to developers, makers, researchers, and users.

The project can also serve as a reference implementation for building browser-based interfaces for BLE-enabled hardware.

## Development

Clone the repository:

```bash
git clone https://github.com/burdva/checkmygas.com.git
cd checkmygas.com
```

Because the application is a web project, it can be served using any standard static web server.

For local development, for example:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

> Note: Web Bluetooth generally requires a secure context such as HTTPS or an appropriate local development environment. Browser security policies may prevent BLE access when the application is served from an insecure origin.

## Architecture

CheckMyGas is intentionally lightweight.

```text
Frontend
   │
   ├── HTML
   ├── CSS
   └── JavaScript
          │
          ▼
   Web Bluetooth API
          │
          ▼
     BLE Connection
          │
          ▼
   Burdva GM-1000
```

The web application communicates directly with the hardware where supported. The BLE communication does not inherently require a backend server.

## Use Cases

CheckMyGas can be useful for:

* LPG level monitoring
* Testing GM-1000 hardware
* Device development and debugging
* BLE experimentation
* Hardware demonstrations
* Building custom interfaces around the GM-1000
* Developers integrating the GM-1000 into other applications

## Future Possibilities

Potential extensions include:

* LPG consumption history
* Low-level notifications
* Historical charts
* Multiple GM-1000 device support
* Device diagnostics
* Calibration tools
* LPG usage analytics
* Local data storage
* Exporting measurement data
* Progressive Web App support
* Integration with home automation systems
* Integration with other Burdva IoT devices

## Related Hardware

**Burdva GM-1000**

An LPG monitoring device developed by **Burdva Limited**.

The GM-1000 communicates with compatible clients using Bluetooth Low Energy.

## Contributing

Contributions are welcome.

You can contribute by:

* Reporting bugs
* Improving the user interface
* Improving BLE communication
* Adding browser compatibility
* Improving documentation
* Adding tests
* Proposing new features
* Building integrations

To contribute:

```bash
git checkout -b feature/your-feature
```

Make your changes, then commit and push:

```bash
git add .
git commit -m "Add your feature"
git push origin feature/your-feature
```

Open a pull request against the `main` branch.

## License

This project is open source.

See the repository license for the terms governing use, modification, and distribution.

## Links

**CheckMyGas:**
https://checkmygas.com

**Source Code:**
https://github.com/burdva/checkmygas.com

**Burdva:**
https://burdva.com

---

### Built for the GM-1000

**CheckMyGas** provides a simple bridge between the physical world and the browser, allowing the Burdva GM-1000 to be accessed directly through Bluetooth Low Energy.
