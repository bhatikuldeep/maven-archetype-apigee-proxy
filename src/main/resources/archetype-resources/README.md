# ${proxyname}
${description}

## Deploy Proxy
```bash
mvn install -Pdefault -Denv.APIGEE_ORG=euw1-partner05 -Denv.APIGEE_ENV=test -Denv.APIGEE_USERNAME=kuldeep.bhati@devoteam.com -Denv.APIGEE_PASSWORD=****************
```

## Some notes
- Ensure config.json has all requried environment
- Ensure, all corresponding postman collections file exist with `${env}.postman_environment.json`, for e.g. `"prod.postman_environment.json"` under `/test` directory if trying to deploy to prod;
- Change `-Denv.API_DOMAIN` accordingly when deploy to a specific apigee domain. 