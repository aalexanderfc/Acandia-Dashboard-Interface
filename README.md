# Acandia Modbus Data Dashboard Interface

This project is a Modbus Data Dashboard developed by **Acandia AB** for monitoring and managing LoRaWAN-based devices connected to a Robustel router. The solution is designed to visualize telemetry data, manage devices, and provide detailed register information through an intuitive web interface.

---

## 📋 Features

✅ Device Management System for LoRaWAN devices  
✅ Automatic data visualization via Modbus registers  
✅ Real-time telemetry updates  
✅ Customizable dark mode for enhanced UI experience  
✅ Detailed view for Modbus registers with associated telemetry data  
✅ Manual search and confirmation of pending devices  
✅ Automatic time zone adjustment based on router settings  

---

## 📂 Project Structure

```
modbus_dashboard_installer/
├── src/
│   ├── app.py
│   ├── modbus_handler.py
│   ├── mqtt_client.py
│   ├── modbus_data.json
│   └── ... (other Python files)
├── templates/
│   ├── index.html
│   ├── device_management.html
│   └── data_table.html
├── static/
│   ├── css/
│   ├── js/
│   └── img/
├── diagram.png
├── install.sh
├── modbus_dashboard.service
├── requirements.txt
└── README.md
```

---

## 🖥️ System Architecture

The following diagram outlines the architecture of the system:

![System Architecture](diagram.png)

---

## 🛠️ Installation Instructions

### Step 1: Clone the Repository
```bash
git clone https://github.com/AcandiaAB/modbus_dashboard_installer.git
cd modbus_dashboard_installer
```

### Step 2: Run the Installer
```bash
chmod +x install.sh
./install.sh
```
This script will:
- Install system dependencies (Python, pip, etc.)
- Copy project files to `/opt/modbus_dashboard/`
- Install required Python dependencies from `requirements.txt`
- Setup the systemd service to ensure the app runs on startup

### Step 3: Enable the Service
```bash
sudo systemctl start modbus_dashboard.service
sudo systemctl enable modbus_dashboard.service
```

### Step 4: Verify the Installation
```bash
sudo systemctl status modbus_dashboard.service
```
If everything is working correctly, the service should be `active (running)`.

---

## 📷 Screenshots

### Device Management
![Device Management](DeviceManagement.png)

### Data Table with Modbus Registers
![Data Table](DataTable.png)

### Add New Device
![Add New Device](addNewDevice.png)

### Slave ID Assignment
![Slave ID Assignment](SlaveID-Assignment.png)

### Home Page
![Home Page](Homepage.png)

---

## 🚀 How to Use

1. **Add New Devices:** Click on `Search for New Devices`, confirm the device, and assign a Slave ID.  
2. **Monitor Telemetry:** View updated telemetry data in the device cards.  
3. **View Registers:** Click `View Registers` to inspect detailed device information.  
4. **Manage Devices:** Navigate to the `Device Management` tab for deleting or modifying devices.  

---

## 🔧 Technologies Used

- **Python** (Flask, Pymodbus, Paho-MQTT)  
- **HTML / CSS / JavaScript**  
- **Systemd** (For auto-starting the application)  
- **Robustel Router** (LoRaWAN & MQTT)  
- **JSON** (For data storage)  

---

## 📈 Future Improvements

🔹 Add device grouping for easier navigation  
🔹 Implement advanced data visualization with Grafana integration  
🔹 Improve alert system for unexpected telemetry values  

---

## 📩 Contact Information

For questions, support, or feature requests, feel free to contact us at:  
📧 **info@acandia.se**

