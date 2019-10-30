# ds2-tfjs-node-red
A Node-RED application to use ds2-tfjs and node-red-contrib-ds2-tfjs

### Clone this repo

Clone this repo and get into the directory
```
git clone https://github.com/yhwang/ds2-tfjs-node-red.git
cd ds2-tfjs-node-red
```

### Create Self Signed Certificate

In order to access the microphone inside a browser, the Node-RED shall run
on HTTPS. The following steps use `openssl` utility to create a privdate key
and a self-signed certificate
- `privatekey.pem`: the private key
- `certificate.pem`: the self-signed certificate
```
openssl genrsa -out privatekey.pem 2048
openssl req -new -sha256 -key privatekey.pem -out node-csr.pem
openssl x509 -req -in node-csr.pem -signkey privatekey.pem -out certificate.pem
```

### Build this project

Then initialize the `ds2-tfjs-node-red` project.
```
npm install
```

### Start the Node-RED instance

Start the Node-RED with the example flow. And access the editor at
https://localhost:1880

```
npm run start
```
