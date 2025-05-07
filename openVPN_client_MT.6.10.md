############################################
# OpenVPN client profile for MikroTik 6.49.10
# (bez tls-auth)
############################################

client
dev tun
proto tcp-client

# wpisz tutaj adres lub DNS serwera i port TCP
remote <TWÓJ_SERVER_IP_LUB_DNS> <PORT_TCP>

# utrzymywanie połączenia
resolv-retry infinite
nobind
persist-key
persist-tun

# dostosowanie do RouterOS 6.x
cipher BF-CBC
auth SHA1

# weryfikacja certyfikatu serwera (opcjonalnie, ale zalecane)
remote-cert-tls server

# kompresja LZO (jak na MikroTiku)
comp-lzo yes

# poziom logów (możesz zwiększyć do 4-5 dla debugowania)
verb 3



############################################
# Sekcja certyfikatów i kluczy
# Pamiętaj, by podmienić zawartość każdego
# bloku na wygenerowane u Ciebie pliki!
############################################

<ca>
-----BEGIN CERTIFICATE-----
# tutaj wklej zawartość pliku ca.crt
-----END CERTIFICATE-----
</ca>

<cert>
-----BEGIN CERTIFICATE-----
# tutaj wklej zawartość pliku client.crt
-----END CERTIFICATE-----
</cert>

<key>
-----BEGIN RSA PRIVATE KEY-----
# tutaj wklej zawartość pliku client.key
-----END RSA PRIVATE KEY-----
</key>
