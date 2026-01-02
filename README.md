# Weblab 04: Secure server

This project consists of configuring a secure server using the HTTPS protocol in Apache, using self-signed certificates for the domain `discovery.sistema.sol`.

## Objective
Configure secure access (port 443) and verify the correct implementation of SSL/TLS encryption on the previously virtualized network infrastructure.

## Configuration Steps

### 1. Generating the Self-Signed Certificate
The `openssl` tool was used to generate a private key and a certificate valid for 365 days:
```bash
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout /etc/ssl/private/apache-selfsigned.key \
  -out /etc/ssl/certs/apache-selfsigned.crt
```
Next, once the certificate has been generated and the certificate (.crt) and key (.key) have been entered in the `/etc/ssl` directory, we configure the configuration file, which we have named **discovery-ssl.conf**.
[CONFIGURATION_FILE](./images/conf_file.png)