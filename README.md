## Ejemplo contrato inteligente

Instalar hlf-saas-cli:

### Linux

Ejecutar los siguientes comandos:
```bash
VERSION=0.0.6
wget "https://github.com/kfsoftware/hlf-saas-cli-releases/releases/download/v${VERSION}/hlf-saas-cli_${VERSION}_linux_amd64.tar.gz"
tar -zxvf hlf-saas-cli_${VERSION}_linux_amd64.tar.gz
sudo mv hlf-saas-cli /usr/local/bin/hlf-saas-cli
```

### Windows

Descargue este tar.gz, extráigalo y agréguelo a un directorio que este en el PATH del sistema:
https://github.com/kfsoftware/hlf-saas-cli-releases/releases/download/v0.0.6/hlf-saas-cli_0.0.6_windows_amd64.tar.gz

### Apple AMD
Download this tar.gz, extract it and add it to the bin:

```bash
VERSION=0.0.6
wget "https://github.com/kfsoftware/hlf-saas-cli-releases/releases/download/v${VERSION}/hlf-saas-cli_${VERSION}_darwin_amd64.tar.gz"
tar -zxvf hlf-saas-cli_0.0.6_darwin_amd64.tar.gz
sudo mv hlf-saas-cli /usr/local/bin/hlf-saas-cli
```

Replace VERSION with the version in the linux section above.


### Apple Sillicon

Descargue este tar.gz, extráigalo y agréguelo a un directorio que este en el PATH del sistema:
```bash
VERSION=0.0.6
wget "https://github.com/kfsoftware/hlf-saas-cli-releases/releases/download/v${VERSION}/hlf-saas-cli_${VERSION}_darwin_arm64.tar.gz"
tar -zxvf hlf-saas-cli_0.0.6_darwin_arm64.tar.gz
sudo mv hlf-saas-cli /usr/local/bin/hlf-saas-cli
```

### Login

```bash
hlf-saas-cli auth login
```

```bash
hlf-saas-cli dev start --localChaincode="localhost:9999" --chaincode=jviejo_ejercicio --env-file=.env
```

```bash
hlf-saas-cli dev listen --forward-to=localhost:9999
```

```bash
npm run desarrollo contrato
```

## Probar chaincode

Acceder a [https://hlf-cc-dev.k8s.kfs.es/playground](https://hlf-cc-dev.k8s.kfs.es/playground)

```graphql
mutation initLedger {
  invokeChaincode(
    input: {
      chaincodeName: "<usuario>_ejercicio"
      function: "InitLedger"
      args: []
      transientMap: []
    }
  ) {
    response
    transactionID
    chaincodeStatus
  }
}

mutation queryAsset {
  queryChaincode(
    input: {
      chaincodeName: "<usuario>_ejercicio"
      function: "GetAllAssets"
      args: []
      transientMap: []
    }
  ) {
    response
    chaincodeStatus
  }
}
```
