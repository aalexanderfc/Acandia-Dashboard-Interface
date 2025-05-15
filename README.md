# **Acandia Modbus Data Dashboard Interface**

### **Author**: Alexander Flores

---

## **Introduction**

This proprietary solution, developed by **Alexander Flores** for **Acandia AB**, runs directly on Acandia’s Robustel routers. It acts as a bridge that **converts incoming LoRaWAN telemetry into Modbus registers** while offering a web interface for device management, live data visualisation and full insight into the register map.

---

## 📋 **Key Features**

✅ Device‑management system for LoRaWAN devices
✅ Automatic data visualisation via Modbus registers
✅ Real‑time telemetry updates in an intuitive UI
✅ Customisable dark mode for better user experience
✅ Detailed view of Modbus registers and associated telemetry
✅ Manual search and approval of pending devices
✅ Automatic time‑zone alignment with router settings

---

## 🖥️ **System Architecture**

![System Architecture](diagram.png)

---

## 📷 **Interface Highlights**

### Device Management

Add, approve or reject connected devices in a single click.

![Device Management](DeviceManagement.png)

### Data Table with Modbus Registers

Visualise live data and inspect register‑level details.

![Data Table](DataTable.png)

### Add New Device

On‑board new LoRaWAN nodes and assign Modbus slave IDs in one step.

![Add New Device](addNewDevice.png)

### Slave ID Assignment

Manage Modbus addressing through a dedicated screen.

![Slave ID Assignment](SlaveID-Assignment.png)

### Home Page

Dashboard overview listing all devices and their latest readings.

![Home Page](Homepage.png)

---

## 🔧 **Technologies Used**

* **Python** (Flask, Pymodbus, Paho‑MQTT)
* **HTML / CSS / JavaScript**
* **systemd** (for automatic startup)
* **Robustel Router** (LoRaWAN & MQTT)
* **JSON** (lightweight data storage)

---

## 🏭 **Why Translate LoRaWAN to Modbus?**

1. **Industry‑wide OT standard** – Modbus (TCP/RTU) is the *lingua franca* for SCADA, PLC, BMS/HVAC and other industrial control systems. Exposing LoRaWAN sensor data as Modbus registers lets existing plants consume wireless measurements without upgrading their control infrastructure.
2. **Long range meets low power** – LoRaWAN delivers battery‑powered sensors over kilometres. Converting to Modbus puts those remote values on the control‑room screen as if they were wired.
3. **Seamless IT/OT integration** – Performing the bridge inside the router removes the need for extra gateways or cloud middleware. IT can still push MQTT to the cloud, while OT can poll Modbus locally.
4. **Compliance & validation** – Regulated sectors (water, energy, process industries) often require that process data be available in Modbus or OPC formats for audit trails and control loops.

**Bottom line:** *One wireless sensor fleet can feed both cloud APIs and traditional SCADA without duplicate integrations.*

---

## 📑 **Register Map (example)**

| Address (Holding) | Parameter        | Data Type | Description                       |
| ----------------- | ---------------- | --------- | --------------------------------- |
| 40001             | Temperature      | INT16     | Sensor temperature in °C × 10     |
| 40002             | Humidity         | UINT16    | Relative humidity % × 10          |
| 40003             | BatteryVoltage   | UINT16    | Battery voltage in mV             |
| 40004             | RSSI             | INT16     | Signal strength dBm               |
| 40010 – 40019     | CustomSensor1‑10 | FLOAT32   | Application‑specific values       |
| 40100             | DeviceStatus     | UINT16    | 0 = OK, 1 = LowBattery, 2 = Fault |

> **Note:** Register addresses are project‑configurable. The table shows a typical default schema shipped with the dashboard.

---

## 🏠 **Benefits of Local Processing in the Router**

* **No cloud or internet dependency** – Operation continues even during WAN outages.
* **Millisecond latency to SCADA/PLC** – All logic runs on the same hardware that answers Modbus requests.
* **Lower CAPEX** – Eliminates the need for separate industrial PCs or edge gateways.
* **Data sovereignty & security** – Telemetry never leaves the site unless you want it to.
* **Centralised configuration** – The router is already the IT/OT bridge; hosting the conversion here simplifies operations.

---

## ❗ **Important Notice**

This project is proprietary software owned by **Acandia AB** and intended strictly for internal use. Unauthorised distribution, installation or modification is prohibited.

---

## 📩 **Contact**

For questions about the solution or internal deployment, please contact:
📧 **[alexander.flores@acandia.se](mailto:alexander.flores@acandia.se)**
