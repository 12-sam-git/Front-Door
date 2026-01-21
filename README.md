# Azure Front Door – VM and Static Website Integration

## 📌 Project Overview
This project demonstrates how to configure **Azure Front Door (Standard)** to serve content from **multiple backend origins** using a **single global endpoint**.

The setup includes:
- An **Azure Virtual Machine** hosting a dynamic web application
- An **Azure Storage Account** hosting a static website
- **Path-based routing** using Azure Front Door

This Proof of Concept (POC) showcases how Azure Front Door can act as a **global CDN and Layer-7 load balancer**.

---

## 🎯 Problem Statement
Organizations often need to expose multiple applications (dynamic and static) through a **single public URL** while ensuring:
- High performance
- Global accessibility
- Simplified routing and management

This project solves that problem using **Azure Front Door**.

---

## 🏗️ Architecture

User Request Flow:

User (Browser)  
→ Azure Front Door (Global Entry Point)  
→ Azure VM (Dynamic App) **OR**  
→ Azure Storage (Static Website)

---

## ☁️ Azure Services Used

- **Azure Front Door (Standard)**
- **Azure Virtual Machine**
- **Azure Storage Account (Static Website)**
- **Azure Networking (NSG, Public IP)**

---

## 🔀 Routing Logic

| Path Pattern | Backend Origin |
|--------------|---------------|
| `/app/*` | Azure Virtual Machine |
| `/*` | Azure Storage Static Website |

---

## ⚙️ Configuration Summary

### Azure Virtual Machine
- Web server installed (Apache / IIS / Nginx)
- Application running on port 80 or 443
- Public IP enabled
- NSG allows HTTP/HTTPS traffic

### Azure Storage Account
- Static Website feature enabled
- `index.html` uploaded
- HTTPS endpoint configured

### Azure Front Door
- Two origin groups:
  - VM Origin Group
  - Storage Origin Group
- Path-based routing configured
- Single Front Door endpoint exposed

---

## 🧪 Testing & Validation

### Test Dynamic Application

