# Shibboleth-Metadata-certificate
Small bash utility to get X509Certificate from Shib Metadata correctly formatted


Create a new file "text" and copy certificate from metadata like in the example:

-----BEGIN CERTIFICATE-----
#certificate copied from web page
-----END CERTIFICATE-----


-----BEGIN CERTIFICATE-----
MIIF5DCCA8ygAwIBAgIIU7VD5jwergergergEGHTBsdExIDAeB....NJQ1QxFzAVBgNV BAMTDml>
-----END CERTIFICATE-----

then:


fold -w 64 text > cert
openssl x509 -in cert -out example.pem
openssl x509 -text -in example.pem
