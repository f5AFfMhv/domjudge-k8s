## Create self-signed certificate

```bash
# Generate key
openssl genrsa -out domserver.example.com.key 2048
# Create certificate signing request
openssl req -new -key domserver.example.com.key -out domserver.example.com.csr
# Create public certificate
openssl x509 -req -days 365 -in domserver.example.com.csr -signkey domserver.example.com.key -out domserver.example.com.crt
# Verify certificate
openssl x509 -in domserver.example.com.crt -text -noout
```

Update `Caddyfile` with certificate and key file names.