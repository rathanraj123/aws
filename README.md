# AWS Starter Project

A beginner-friendly static website for practising AWS deployment.

## Files
- `index.html` — page structure
- `style.css` — design
- `script.js` — button interaction

## Run locally
Open `index.html` in your browser. No installation or build command is required.

## Deploy on an Ubuntu EC2 instance (Apache)

1. Connect to your EC2 instance using SSH.
2. Install Apache:

   ```bash
   sudo apt update
   sudo apt install apache2 -y
   ```

3. Start Apache and enable it at boot:

   ```bash
   sudo systemctl enable --now apache2
   ```

4. Copy the website files into Apache's web root. Run this from the project folder:

   ```bash
   sudo cp index.html style.css script.js /var/www/html/
   ```

5. In the EC2 Security Group, allow inbound HTTP traffic on port **80** from `0.0.0.0/0`.
6. Open `http://YOUR-EC2-PUBLIC-IP` in a browser.

## Important
- No database, backend, secrets, build tools, or paid service dependency.
- Keep SSH (port 22) restricted to your own IP address.
- Add a domain and TLS certificate later if you need HTTPS.
