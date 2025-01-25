### OPENVPN
Create CA certificate, key usage “crl sign”, “key cert sign”. Sign certificate. Make trusted.

Create Server certificate, key usage “digital signature”, “key enchipherment”, “tls server”. Sign with CA certificate. Make Trusted.

Create Client certificate, key usage “tls client”. Sign with CA certificate. Make trusted.

Set Server certificate on OVPN server.

Import the CA & Client (with key) certificates into client. Set Client certificate in client connection.