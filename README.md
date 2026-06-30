# Contabo WHMCS Automation Module

**Developed by:** Cloud Web Nepal  
**Whatapp Plugins Support And License:** +977-9845870006  
**Anually License Fee:** Only 12$/yr and in NPR Rs 1500  
**Website:** [https://cloudwebnepal.com]
  

---

Thank you for choosing Cloud Web Nepal! This package contains a complete, enterprise-grade integration for Contabo Cloud VPS. 
It consists of two parts:
1. **The Server Module (`contabo`)** - Handles VPS Provisioning and Client Area management.
2. **The Addon Module (`contabo_dashboard`)** - The Global Admin Dashboard and Licensing Engine.

## Installation Instructions

1. **Server Module:** Copy the `contabo` folder and paste it into your WHMCS directory at:  
   `WHMCS_ROOT/modules/servers/`

2. **Dashboard & Licensing Module:** Copy the `contabo_dashboard` folder and paste it into:  
   `WHMCS_ROOT/modules/addons/`

3. **UI Hooks:** Copy the `includes` folder and paste it directly into your WHMCS root directory:  
   `WHMCS_ROOT/`

---

## Step 1: License Activation (CRITICAL)

The Contabo module features a secure, cached licensing system. **The module will not function until a valid license is activated.**

1. Log in to your WHMCS Admin Area.
2. Navigate to **System Settings -> Addon Modules**.
3. Find **Contabo VPS Dashboard** and click **Activate**.
4. Click **Configure**.
5. Tick the checkboxes to grant access to your administrator roles (e.g., "Full Administrator").
6. **Enter your License Key** in the "License Key" text box. (Obtained from Cloud Web Nepal).
7. Click **Save Changes**.

*To verify your license is working, navigate to **Addons -> Contabo VPS Dashboard** and check the **License Details** tab.*

---

## Step 2: Server Setup

1. Navigate to **System Settings -> Products/Services -> Servers**.
2. Click **Add New Server**.
3. Fill in the details:
   - **Name:** Contabo Primary
   - **Hostname:** api.contabo.com
   - **Type:** Contabo Cloud VPS (Select this from the dropdown)
   - **Username:** [Your Contabo Control Panel Email]
   - **Password:** [Your Contabo API Password - GENERATE THIS IN CONTABO PANEL]
4. **API Client Credentials:**
   Once you select "Contabo Cloud VPS" from the dropdown, the standard WHMCS Access Hash box will automatically split into two separate fields:
   - **Contabo Client ID:** Enter your OAuth2 Client ID
   - **Contabo Client Secret:** Enter your OAuth2 Client Secret
5. Click **Save Changes**.

> **IMPORTANT NOTE ON PASSWORD:** Do NOT use your normal Contabo Control Panel login password. Contabo requires a dedicated API Password. You must generate this in the Contabo Panel under *Customer Data -> Security -> API Password*.

---

## Step 3: Product Configuration

1. Navigate to **System Settings -> Products/Services -> Products/Services**.
2. Create a new Product, or edit an existing one.
3. Go to the **Module Settings** tab.
4. Select **Contabo Cloud VPS** from the Module Name dropdown.
5. Fill in the configuration fields:
   - **Region:** e.g., `EU`, `US-central`
   - **Product ID:** e.g., `V6` for VPS S, `V7` for VPS M
   - **Default Image ID:** The UUID of the OS image (e.g., `f4d54694-8ab3-4cda-92c9-6e3e56a4cf88` for Ubuntu 20.04)
   - **Hostname Prefix:** e.g., `vps-` (Used if the client doesn't provide a hostname).
6. Configure automation rules (e.g., "Automatically setup the product as soon as the first payment is received").
7. Click **Save Changes**.

---

## Features included

### Client Area (Automated)
- Beautiful, responsive dashboard built with modern CSS and Bootstrap.
- **Power Controls:** Start, Stop, Reboot, Shutdown.
- **Snapshots:** Create, Restore, and Delete snapshots instantly.
- **Rebuild OS:** Customers can reinstall their OS automatically using Image IDs.
- **Password Reset:** Securely reset the root password.
- **Activity Logs:** Dedicated tab showing chronological logs of all power actions.
- **Animated Warning Modals:** Smooth SweetAlert-style confirmation dialogues to prevent accidental clicks.

### Admin Dashboard (`Addons -> Contabo VPS Dashboard`)
- **Instances Overview:** A global table listing all VPS instances fetched directly from the Contabo API.
- **WHMCS Syncing:** Easily see which servers are unassigned and assign them to WHMCS clients directly from the dashboard.
- **Global Activity Logs:** A searchable, master log of every action performed on any Contabo VPS across your entire system.
- **License Details:** Real-time visibility into your Cloud Web Nepal license status, expiry, and caching.
