### OPENVPN
Create CA certificate, key usage “crl sign”, “key cert sign”. Sign certificate. Make trusted.

Create Server certificate, key usage “digital signature”, “key enchipherment”, “tls server”. Sign with CA certificate. Make Trusted.

Create Client certificate, key usage “tls client”. Sign with CA certificate. Make trusted.

Set Server certificate on OVPN server.

Import the CA & Client (with key) certificates into client. Set Client certificate in client connection.

### OPENVPN 6.10 MT

## Certyfikat CA – OpenVPN
[COMMON NAME: example.pl]
- crt sign
- key cert. sign

## Generowanie certyfikatu dla serwera
[COMMON NAME: *.example.pl]
- digital signature 
- key enciphement
- data enciphement [optymalnie]
- tls server

## Generowanie certyfikatu dla klienta
[COMMON NAME: user.example.pl]
- tls client

https://netadminpro.pl/konfiguracja-openvpn-przy-pomocy-mikrotika/