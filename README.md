# ds2-tfjs-node-red
A Node-RED application to use ds2-tfjs and node-red-contrib-ds2-tfjs

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

### Sync submodule

Some dependent modules are not published to npm repository
yet. They are linked as submodules for now. Here are the steps
to clone these projects into corresponding directories.

```
git submodule update --remote --rebase
```

### Build ds2-tfjs submodule

When submodules are downloaded, we need to initialize and build
these submodules first. First of all, start with the `ds2-tfjs` module.
Make sure that you are in the `ds2-tfjs-node-red` folder before
you execute the following commands.
```
cd ds2-tfjs
npm install
npm run build
```

### Build node-red-contrib-ds2-tfjs submodule

Then initialize and build the `node-red-contrib-ds2-tfjs`
custom node. Make sure that you are in the `ds2-tfjs-node-red`
folder before you execute the following commands.
```
cd node-red-contrib-ds2-tfjs
npm install
npm run build
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