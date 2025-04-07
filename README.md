# Mortgage Calculator Web App

## Contact Information
- **Name**: Asis Hang Rai
- **Email**: arenrai18@gmail.com
## Overview
This project involves the development of a **Mortgage Calculator** web application hosted on an **Ubuntu Server** running on an AWS EC2 instance. The website is accessible via the domain **mortagecalculator.click**. This project integrates **SSL** for security, **DNS** for domain management, and a **cloud server** for hosting.

- **Web Server**: Apache on Ubuntu Server
- **SSL**: Let's Encrypt with Certbot
- **Cloud Hosting**: AWS EC2
- **DNS Management**: AWS Route 53
- **License**: MIT License
- 
## Setup Process
### 1. Launching and Connecting to the EC2 Instance
   - Launched an **Ubuntu 20.04 EC2 instance** on AWS.
   - Configured **Elastic IP** to ensure the instance has a static IP address.
   - Opened necessary **ports** (80 for HTTP, 443 for HTTPS, and 22 for SSH) in the AWS security group to allow external access to the server.

#### 1.1 **Connecting EC2 Instance to Ubuntu via SSH**
   - During EC2 instance setup, created a **key pair** named `my-key.pem` and downloaded it to my local machine.
   - Moved the key file to a secure location and set proper permissions:
     ```bash
     chmod 400 ~/Downloads/ubuntu.pem
     ```
   - Connected to the EC2 instance from my local Ubuntu machine using the terminal:
     ```bash
     ssh -i ~/Downloads/ubuntu.pem ubuntu@65.2.161.89
     ```
   - Accepted the authenticity prompt and successfully accessed the EC2 server.

### 2. **Installing Apache Web Server**
   - **Updated the package list** on the server:
     ```bash
     sudo apt update
     ```
   - **Installed Apache** web server:
     ```bash
     sudo apt install apache2
     ```
   - **Checked Apache status** to ensure it was running:
     ```bash
     sudo systemctl status apache2
     ```
   - **Started Apache** service (if not started automatically):
     ```bash
     sudo systemctl start apache2
     ```

### 3. **Configuring Apache for the Project**
   - Edited the **Apache configuration file** (`/etc/apache2/sites-available/000-default.conf`) to set up the site:
     - Set the `DocumentRoot` to point to the folder where the project files are located.
   - Restarted Apache to apply changes:
     ```bash
     sudo systemctl restart apache2
     ```

### 4. **Setting Up DNS Using namecheap.com and AWS Route 53**
   - **Namecheap.com** 
   - Used namecheap.com to get a domain name and pinged it to my server
   - **Accessed AWS Route 53** from the AWS Management Console.
   - Created a **hosted zone** for the domain `mortagecalculator.click` in Route 53.
   - Created a new **A record** to point to the **Elastic IP** (65.2.161.89) of the EC2 instance:
     - **Name**: `mortagecalculator.click`
     - **Type**: `A - IPv4 address`
     - **Value**: `65.2.161.89` (Elastic IP of the EC2 instance)
   - Ensured that the **TTL** (Time to Live) was set to 300 seconds for quicker propagation.
   - Updated the **domain registrar** settings to point to **AWS Route 53’s nameservers** provided by the hosted zone.

### 5. **SSL/TLS Setup with Let's Encrypt**
   - **Installed Certbot** and the Apache plugin:
     ```bash
     sudo apt install certbot python3-certbot-apache
     ```
   - **Obtained the SSL certificate** using Certbot:
     ```bash
     sudo certbot --apache
     ```
   - Followed the interactive prompts to:
     - Confirm domain ownership.
     - Configure Apache to automatically redirect HTTP traffic to HTTPS.
   - **Tested SSL** by visiting `https://mortagecalculator.click` and ensuring that the site was served securely.

### 6. **Deploying the Mortgage Calculator Web App**
   - Developed the **Mortgage Calculator** using **HTML**, **CSS**, and **JavaScript**:
     - Designed the form to input the loan amount, interest rate, and term.
     - Implemented JavaScript to perform the mortgage calculation.
   - **Placed the application files** in the Apache web server's root directory (`/var/www/html`).

### 7. **Testing the Web App**
   - Accessed the website via the domain `https://mortagecalculator.click` from a web browser.
   - **Tested all functionalities** of the mortgage calculator to ensure accuracy in calculations.
   - Verified that the website was correctly served over **HTTPS** and SSL certificate was valid.

### 8. **Documenting the Project**
   - Created this **README.md** file to provide an overview and detailed steps of the project.
   - **Committed the changes** to the project repository using Git:
     ```bash
     git add README.md
     git commit -m "Detailed README with step-by-step instructions and EC2 SSH setup"
     git push
     ```

## Development Timeline
- **Week 3-5**:
    - Set up the server on AWS EC2 instance with Ubuntu.
    - Configured domain DNS to point to the server's IP address.
    - Installed Apache on the server.
    - Connected to EC2 instance from Ubuntu via SSH.

- **Week 6-10**:
    - Developed the basic structure of the mortgage calculator using HTML, CSS, and JavaScript.
    - Installed and configured SSL/TLS using Certbot on Apache to secure the website.
    - Tested the server's accessibility via the domain name.
    - Finalized the mortgage calculator functionality.
    - Completed the SSL/TLS configuration and ensured HTTPS was working correctly.
    - Added all the required documentation to the repository.
    - Created a MIT Lisence file
- **Week 11**:
    - Completed the final testing, making sure everything was functioning as expected.
    - Pushed the final changes to the GitHub repository.


---

### Additional Information:
- **Access the site**: The website can be accessed at [https://mortagecalculator.click].
.
