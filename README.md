# Shibboleth-Metadata-certificate
Small bash utility to get X509Certificate from Shib Metadata correctly formatted


Create a new file "text" and copy certificate from metadata:  

-----BEGIN CERTIFICATE-----  
#certificate copied from web page  
-----END CERTIFICATE-----  

for example:  

-----BEGIN CERTIFICATE-----  
MIIF5DCCA8ygAwIBAgIIU7VD5jwergergergEGHTBsdExIDAeB....NJQ1QxFzAVBgNV BAMTDwfECds>  
-----END CERTIFICATE-----  

then:  


fold -w 64 text > cert  
openssl x509 -in cert -out example.pem  
openssl x509 -text -in example.pem  
