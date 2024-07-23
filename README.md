# BestStoreMVC Application


https://github.com/user-attachments/assets/4de3b634-5a7d-4ce3-8891-8aba50c43264


## Overview
BestStoreMVC is an ASP.NET Core MVC web application that demonstrates how to perform CRUD (Create, Read, Update, Delete) operations using Entity Framework Core and SQL Server. The application allows users to manage a list of products, including uploading images for each product.

## Features
- List products
- Create a new product
- Edit an existing product
- Delete a product
- Upload and display product images

## Prerequisites
- .NET 7.0 SDK
- SQL Server
- Visual Studio 2022 (recommended for development)

## Configuration
### appsettings.json
Ensure your `appsettings.json` file contains the correct connection string to your SQL Server instance.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=<Add Your Server Name>;Initial Catalog=BestStoreDb;Integrated Security=True;Trust Server Certificate=True"
  }
}
```
## Database Setup
- Open the Package Manager Console in Visual Studio. Run the following commands to create the database and apply the migrations:

- if you want sql queries copy this queries

```sql
CREATE TABLE Products (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    Name NVARCHAR(100) NOT NULL,
    Brand NVARCHAR(100) NOT NULL,
    Category NVARCHAR(100) NOT NULL,
    Price DECIMAL(16, 2) NOT NULL,
    Description NVARCHAR(MAX) NOT NULL,
    ImageFileName NVARCHAR(100) NOT NULL,
    CreatedAt DATETIME NOT NULL
);

INSERT INTO Products (Name, Brand, Category, Price, Description, ImageFileName, CreatedAt)
VALUES 
('Gaming Laptop', 'ASUS', 'Laptops', 1299.99, 'High performance gaming laptop', 'gaming_laptop.jpg', GETDATE()),
('Mechanical Keyboard', 'Logitech', 'Keyboards', 79.99, 'RGB mechanical keyboard', 'mechanical_keyboard.jpg', GETDATE()),
('Wireless Mouse', 'Logitech', 'Mice', 49.99, 'Ergonomic wireless mouse', 'wireless_mouse.jpg', GETDATE()),
('27-inch Monitor', 'Dell', 'Monitors', 299.99, '4K Ultra HD monitor', '27_inch_monitor.jpg', GETDATE()),
('External SSD', 'Samsung', 'Storage', 149.99, '1TB portable SSD', 'external_ssd.jpg', GETDATE()),
('Gaming Headset', 'Razer', 'Headsets', 99.99, 'Surround sound gaming headset', 'gaming_headset.jpg', GETDATE()),
('Graphics Card', 'NVIDIA', 'Components', 499.99, 'RTX 3070 graphics card', 'graphics_card.jpg', GETDATE()),
('Motherboard', 'ASUS', 'Components', 199.99, 'Gaming motherboard', 'motherboard.jpg', GETDATE()),
('Processor', 'Intel', 'Components', 329.99, 'Intel i7 processor', 'processor.jpg', GETDATE()),
('RAM', 'Corsair', 'Components', 89.99, '16GB DDR4 RAM', 'ram.jpg', GETDATE()),
('Power Supply', 'EVGA', 'Components', 119.99, '750W power supply', 'power_supply.jpg', GETDATE()),
('Computer Case', 'NZXT', 'Components', 149.99, 'Mid tower computer case', 'computer_case.jpg', GETDATE()),
('Cooling Fan', 'Cooler Master', 'Components', 29.99, 'RGB cooling fan', 'cooling_fan.jpg', GETDATE()),
('Webcam', 'Logitech', 'Accessories', 69.99, '1080p HD webcam', 'webcam.jpg', GETDATE()),
('USB Hub', 'Anker', 'Accessories', 39.99, '7-port USB 3.0 hub', 'usb_hub.jpg', GETDATE()),
('Bluetooth Speaker', 'JBL', 'Audio', 99.99, 'Portable Bluetooth speaker', 'bluetooth_speaker.jpg', GETDATE()),
('Printer', 'HP', 'Printers', 159.99, 'All-in-one wireless printer', 'printer.jpg', GETDATE()),
('Router', 'TP-Link', 'Networking', 89.99, 'Dual band Wi-Fi router', 'router.jpg', GETDATE()),
('HDMI Cable', 'AmazonBasics', 'Cables', 9.99, '6ft HDMI cable', 'hdmi_cable.jpg', GETDATE()),
('Smart Plug', 'TP-Link', 'Smart Home', 19.99, 'Wi-Fi smart plug', 'smart_plug.jpg', GETDATE()),
('NAS', 'Synology', 'Storage', 399.99, '2-bay NAS', 'nas.jpg', GETDATE()),
('Docking Station', 'Dell', 'Accessories', 199.99, 'Universal docking station', 'docking_station.jpg', GETDATE()),
('Laptop Stand', 'Rain Design', 'Accessories', 49.99, 'Aluminum laptop stand', 'laptop_stand.jpg', GETDATE()),
('USB Flash Drive', 'SanDisk', 'Storage', 29.99, '64GB USB 3.0 flash drive', 'usb_flash_drive.jpg', GETDATE()),
('Surge Protector', 'Belkin', 'Accessories', 24.99, '8-outlet surge protector', 'surge_protector.jpg', GETDATE()),
('Ergonomic Chair', 'Herman Miller', 'Furniture', 999.99, 'Ergonomic office chair', 'ergonomic_chair.jpg', GETDATE()),
('USB-C Dock', 'CalDigit', 'Accessories', 249.99, 'USB-C docking station', 'usb_c_dock.jpg', GETDATE()),
('Laptop Cooling Pad', 'Cooler Master', 'Accessories', 49.99, 'Cooling pad for laptops', 'laptop_cooling_pad.jpg', GETDATE()),
('Wireless Charger', 'Anker', 'Accessories', 29.99, 'Fast wireless charger', 'wireless_charger.jpg', GETDATE()),
('Network Switch', 'Netgear', 'Networking', 79.99, '8-port Gigabit Ethernet switch', 'network_switch.jpg', GETDATE());
```

```powershell
Add-Migration InitialCreate
Update-Database
```
This will create the BestStoreDb database with the required tables.

## Running the Application
- Open the solution in Visual Studio.
- Ensure the connection string in appsettings.json is correct.
- Open the Package Manager Console and run the migration commands mentioned above.
- Build and run the application.

## Contributing
Contributions are welcome! Please create an issue or pull request for any features, bug fixes, or improvements.
