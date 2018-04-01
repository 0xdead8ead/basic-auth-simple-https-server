# Basic Auth Simple HTTPS Server

Python SimpleHTTPServer over HTTPS using Basic Auth


### Get Lets Encrypt HTTPS Cert for Server:

A Lets Encrypt TLS certificate can be generated with the following commands

```sh
sudo certbot certonly --register-unsafely-without-email --standalone -d <domain_name>
sudo cat /etc/letsencrypt/live/<domain_name>/fullchain.pem > server.pem
sudo cat /etc/letsencrypt/live/<domain_name>/privkey.pem >> server.pem
```

Alternatively a self signed certificate can be generated with the following command
```sh
openssl req -new -x509 -keyout server.pem -out server.pem -days 365 -nodes
```

### Authorization Key Generation:

Basic Auth Username and Password is generated with the following command

```sh
echo -n "<username>:<password>" | base64
```

### Running the Simple HTTPS Server:

```sh
python simple-https-server_basic-auth.py
```

## Authors

* **Chase Schultz** - *Initial work* - [@f47h3r_b0](https://twitter.com/f47h3r_b0)


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


