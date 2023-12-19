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

## Encoded vs Encrypted vs Signed

1. **Encoded:**
    - **Purpose:** Change the format of data for transmission or storage.
    - **Security:** No real security. It's a reversible transformation, but anyone who knows the encoding method can easily reverse it.
    - **Example:** Base64 encoding. It's like changing the wrapping of a gift but doesn't make it more secure.
2. **Signed:**
    - **Purpose:** Ensure the integrity and authenticity of data.
    - **Security:** Not for secrecy, but to confirm that the data hasn't been tampered with and comes from a trusted source.
    - **How it works:** A unique signature is created based on the content, and others can verify it. If the data changes, the signature won't match.
    - **Example:** Digital signatures in emails. It's like sealing an envelope with your signature to show it hasn't been opened by someone else.
3. **Encrypted:**
    - **Purpose:** Keep data confidential and secure.
    - **Security:** Provides confidentiality by converting data into an unreadable format, and only those with the decryption key can access the original data.
    - **How it works:** Uses algorithms to scramble the data into a format that can only be unscrambled with the correct key.
    - **Example:** HTTPS (secure browsing). It's like putting your message in a locked box, and only the intended recipient with the right key can open it.

In summary:

- **Encoded** is about changing the format.
- **Signed** is about ensuring the data hasn't been tampered with and comes from a trusted source.
- **Encrypted** is about keeping data confidential and secure by making it unreadable without the proper key.
