# HAProxy
Balanceador como container simples 

## Diretórios
Crie a seguinte estrutura de diretórios e/ou ajuste os caminhos nos arquivos.
````
../haproxy/
├── conf
│   └── haproxy.cfg
├── docker-compose.yaml
└── pki
    ├── dhparam.pem
    └── server.pem
````
## Crie um keystore
cat fulchain.pem privkey.pem > ../haproxy/pli/server.pem

## 
