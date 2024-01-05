# Domain-Offensive DNS Authenticator plugin for Certbot

## Installation
```shell
pip install certbot certbot-dns-domainoffensive
```

You can use ```certbot plugins --text``` to verify that the plugin has been installed.

```
$ certbot plugins --text
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
* dns-domainoffensive
Description: Obtain certificates using a DNS TXT record (if you are using
Domain-Offensive for DNS).
Interfaces: IAuthenticator, IPlugin
Entry point: dns-domainoffensive =
certbot_dns_domainoffensive.dns_domainoffensive:Authenticator
...
```

## Configuration
Create a file with your account token in the following format:

```
$ cat /etc/certbot_credentials.ini
dns_domainoffensive_api_token = 02pAPacMv1yNnUzSDR75
```

## Generate a certificate

```shell
certbot certonly --authenticator dns-domainoffensive --dns-domainoffensive-credentials /etc/certbot_credentials.ini --agree-tos -m email@example.de -d *.yourDomain.de
```

## Further information
More detailed explanations and further details on using Certbot can be found on the official website: https://certbot.eff.org/