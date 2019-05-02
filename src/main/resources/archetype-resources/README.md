#set($h1 = '#')
#set($h2 = '##')
#set($h3 = '###')
#set($h4 = '####')

$h1 Proxy Name - ${artifactId}
$h3 Proxy Base Path - ${basepath}
Description - ${description}

$h2 Prerequisite

1. Maven
2. nodeJS
3. set below environment variable according to your requirement (these are referenced in [Deploy Proxy](#deploy-proxy) section)
   - `APIGEE_ORG` - apigee org name
   - `APIGEE_USERNAME` - apigee edge username
   - `APIGEE_PASSWORD` - apigee edge password
4. Postman (optional, to run tests in postman UI)
5. Newman (optional, as it is anyway installed part of dependencies installed while project creation, installed only if it not installed)

$h2 Unit Test
Make sure you have the collection and environment (json files) already under tests folder directory, for advanced use, check pom.xml, execution-id - `integration-tests`

$h2 Deploy Proxy

```sh
$ mvn install -Pdefault -Denv.APIGEE_ORG=$APIGEE_ORG -Denv.APIGEE_ENV=${environment} -Denv.APIGEE_USERNAME=$APIGEE_USERNAME -Denv.APIGEE_PASSWORD=$APIGEE_PASSWORD
```

$h2 Some notes

- Ensure, all corresponding postman collections file exist with `${env}.Postman_environment.json`, for e.g. `"prod.postman_environment.json"` under `/test` directory if trying to deploy to prod;
