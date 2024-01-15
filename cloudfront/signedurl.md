two type of signer 
the recommended way is to use a trusted key group
  leverage api to create and rotate keys and iam for api security 

In our cloudfront distrubution create one or more trusted key group 
We generate our own public key / private key
  basic stuff
    private key used by our application
    public key used by cloudfronts to verify urls 

Lets look at key maangement 
Look at our public key 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9234a6ef-8c2b-40b9-a5b5-fe5280e838e2)

The idea is to gernetate a rsa key 
    private key used by our application
    public key used by cloudfronts to verify urls 
    This will allow our platform url to create signed url 
  Generate RSA key online 2048 bits
  Private
```
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEAiKkpps9wz8T09fppwuo9RHZeVeVymt6AaQUt7rbxF9OH86WR
a38rr4E0GivdMmmZDksQWM90hq+aO+tDQVNob652scSDh0VvgLDsGQFgzlU9C1jA
k4YlaPTsVNzp0bm+YSvI5v3B+j2eQXm0KdBpGY7SrIZpXXeGBUQPohB2YHMI0iKa
mZ1+Q1l9dZveydfwNrI6wScAhbw2EQwJ9skxeCjeGdEzPXm/1F2FnDVhatHJcs73
aHbBLkhYYoHqIBjIsMpN+kVyj6YdMwb2pg20Xaf0yBJUydHn+DxGPizXivDzabzW
qBDiOMt65EksnT5Ch5CZU5bT1QC9F1NJOa/19wIDAQABAoIBADlJuKUt1puydAHd
fJJyAUb+2+LkMZvMZEYiHrQwSnbzfM1dfc1zXQvQfNfvxWVJsRi1zN9979o6KMyv
fd0XqvMOTsGMoJqHOAvZns+IrV0xjEqCZRAyruIFskCM7xO06qLvaOO0Qqm1RO8r
pqPUswo8vgIGwoqk/TCd7HPCtO0PB3RPnQ71EucrLIgx/Ag+RSviZRl/207vP/pV
9UsGUV1IYrkSAjyJRKeGHqO2BGJqgNqrFNxlVUMh8H6VLBpioT2tEHQJxLppmvUm
d4q76WfH7S29LnXJE6vKwQz8BDFGlJtH7ZaInGfXI669XV7Ht/PuPX5nn07TIIx3
fbVeodkCgYEA/9OhB2zHMridBveEsrbt6wvfY/U7Hjwpij4Cl0K6mjSOEIKj3Nrr
vs+McRvRAHKtG52s+qkmM393TCT6Ex5AECyIK/w/GPAFGJecZV1j/qkmdYgdafVq
awWf41qiDAtm3NwQdEY6LpHGQYM9TycFgMcVrOI9GBiWu6/M8xtRhFMCgYEAiMDd
iH26PToTqAsiyjYr6jetb4+O6usD+1c8QSrxVlj+DTYTAFEPRi5EL9CbUXgTDkPy
JHwz8LjcGkv1V2hI0prXyFJoobn1jxZ1rX9ifTrotzC6M4Mk6hDFIuvrK/xgw0cQ
aFKqrtcKohbapSZ8FWes8KFF7Ona5txKjuojE00CgYEAlHCskA1bLCAY5TD762Lf
fDIAZhSmP+3ywIcoo7IRamayQ/w5rm3MuoPdXsggJp1jupFsDGnXg6wjgag2/p7f
10KvpK4RwpuKqXFXSy28Vsi5Sxs2zgObwwuZcadmPYzkG6UJWx5gpiLpoZvQGDxx
If7iodUIVBH4bGEej7U7QIcCgYANB/vUNs7ZaMBYwf7lr/XNUtLnD5H51r1BZRWr
zBDFPqOu1JlI7XB8Kop61/EE+WEvedAIJAG7DZKDuvs9AgX2c6TeROQNjS/WG7jI
+JuE/WkRk8YahIOu/jwa0MpPHbSGxy3MExyKnpk3yt+43wrx6zgykduc8MfYOeOs
7Ki8/QKBgCvHS6L5DM0dMqi7XIl40NBtZ6emnSmthRMP5nFXzZx/8W4xokUgOD+b
oxJBqAQScsu37XVqzdoYU9kcsTdZrB/Ppp/M/qj4fTxj0DX4/EOiT++a4t2dbvLF
4wIdsXhyIf8zpmRhBpTH3cJFhOVAPuonfzBTE84lqFKnQBUAHjsm
-----END RSA PRIVATE KEY-----
```

public 
```
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAiKkpps9wz8T09fppwuo9
RHZeVeVymt6AaQUt7rbxF9OH86WRa38rr4E0GivdMmmZDksQWM90hq+aO+tDQVNo
b652scSDh0VvgLDsGQFgzlU9C1jAk4YlaPTsVNzp0bm+YSvI5v3B+j2eQXm0KdBp
GY7SrIZpXXeGBUQPohB2YHMI0iKamZ1+Q1l9dZveydfwNrI6wScAhbw2EQwJ9skx
eCjeGdEzPXm/1F2FnDVhatHJcs73aHbBLkhYYoHqIBjIsMpN+kVyj6YdMwb2pg20
Xaf0yBJUydHn+DxGPizXivDzabzWqBDiOMt65EksnT5Ch5CZU5bT1QC9F1NJOa/1
9wIDAQAB
-----END PUBLIC KEY-----
```

Create a public key on cloudfront
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/aa6199ad-d204-4f3e-808b-d29e4271d5a6)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3fa6177d-abec-48d2-a3fb-86f958f4ca84)

Create a key group 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9dac3850-1c61-44b4-b242-b832a6b60640)

Add your public key
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/45c89325-7dbf-4fef-b475-bba474d95e4c)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6a12239b-e43b-48ab-9b38-87aaf14538aa)

This will key group will be reference by cloudfront to allow our user to create signed url
