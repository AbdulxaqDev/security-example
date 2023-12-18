# security-example
nodejs security example


Generating self signed ssl certificate:
```bash
$ openssl req -x509 -newkey rsa:4096 -nodes -keyout key.pem -out cert.pem -days 365
```
Explanation:

<code>req</code>: Initiates a new certificate request.

<code>-x509</code>: Specifies the X.509 certificate utility, indicating the creation of a self-signed certificate.

<code>-newkey rsa:4096</code>: Generates a new RSA key with a size of 4096 bits.

<code>-nodes</code>: Stands for "no DES" and means that the private key will not be encrypted, enhancing compatibility with various systems. [read more here](https://stackoverflow.com/questions/5051655/what-is-the-purpose-of-the-nodes-argument-in-openssl)

<code>-keyout file/path/fileName.pem</code>: Specifies the output path and filename for the private key.

<code>-out file/path/fileName.pem</code>: Specifies the output path and filename for the certificate.

<code>-days 365</code>: Sets the validity period of the certificate to 365 days. The default validity period is 30 days.

By using this command, you are requesting a new self-signed SSL certificate, generating a new RSA key, and specifying the output paths for both the private key and the certificate. The <code>-days</code> parameter allows you to customize the validity period of the certificate.
