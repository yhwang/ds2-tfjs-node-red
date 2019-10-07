# ds2-tfjs-node-red
A Node-RED application to use ds2-tfjs and node-red-contrib-ds2-tfjs

### Create Self Signed Certificate

```
openssl genrsa -out privatekey.pem 2048
openssl req -new -sha256 -key privatekey.pem -out node-csr.pem
openssl x509 -req -in node-csr.pem -signkey privatekey.pem -out certificate.pem
```

### Sync submodule

```
git submodule update --remote --rebase
```

### Build ds2-tfjs submodule

```
cd ds2-tfjs
npm install
npm run build
```

### Build node-red-contrib-ds2-tfjs submodule

```
cd node-red-contrib-ds2-tfjs
npm install
npm run build
```

### Build this project

```
npm install
```