# Mortgage Calculator Web App

## Overview
This project involves the development of a **Mortgage Calculator** web application hosted on an **Ubuntu Server** running on an AWS EC2 instance. The website is accessible via the domain **mortagecalculator.click**. This project integrates **SSL** for security, **DNS** for domain management, and a **cloud server** for hosting.

### Technologies Used:t
- **Web Server**: Apache on Ubuntu Server
- **SSL**: Certbot
- **Cloud Hosting**: AWS EC2

## Ubuntu Server Setup
1. **Set up the Ubuntu server** on AWS EC2 instance:
   - Launched an Ubuntu instance on AWS EC2.
   - Configured the EC2 instance to have a static IP for reliable domain binding.

2. **Installed Apache** as the web server:
   - Updated the package list:
     ```bash
     sudo apt update
     ```
   - Installed Apache:
     ```bash
     sudo apt install apache2
     ```

3. **Configured Apache**:
   - Modified the `/etc/apache2/sites-available/000-default.conf` file to set up the domain and point to the appropriate document root.

4. **Installed Certbot for SSL/TLS certificates**:
   - Installed Certbot and the Apache plugin:
     bash
     sudo apt install certbot python3-certbot-apache
     
   - Ran Certbot to obtain and configure SSL for Apache:
     bash
     sudo certbot --apache
     ```

5. **Set up DNS**:
   - Configured the DNS settings to point the domain **mortagecalculator.click** to the server's public IP address (65.2.161.89).

## Development Timeline
- **Week 1**:
    - Set up the server on AWS EC2 instance with Ubuntu.
    - Configured domain DNS to point to the server's IP address.

- **Week 2**:
    - Installed Apache on the Ubuntu server.
    - Developed the basic structure of the mortgage calculator using HTML, CSS, and JavaScript.

- **Week 3**:
    - Implemented SSL/TLS using Certbot on Apache to secure the website.
    - Tested the DNS and SSL configurations to ensure the website is accessible over HTTPS.

- **Week 4**:
    - Completed the final deployment and tested server accessibility.
    - Added detailed documentation to the project repository.

## Contact Information
- **Name**: [ASIS HANG RAI Student ID:35524152]
- **Email**: arenrai18@gmail.com

---

### Additional Information:
- **Access the site**: The website can be accessed at [https://mortagecalculator.click](https://mortagecalculator.click).
- **SSL/TLS**: The site is secured with SSL/TLS using Let's Encrypt, ensuring all traffic is encrypted.

