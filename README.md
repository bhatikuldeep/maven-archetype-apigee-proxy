# Apigee Edge - Proxy Template Generator (with maven archtype)

## version 1.3 - with Apigee Edge Environment Configuration Support

This is an effort to automate apigee edge proxy generation - with custom maven archtype.
Use this project to create a apigee edge proxy skeleton, you can create and upload a sample proxy in few steps.
This project will create a sample proxy project directory only, in order to deploy, please follow instruction [below](#how-to-use-it);

Feature supported;

- Proxy Template with basic flow - √
- Integration Tests (with postman/newman) - √
- Accept Proxy Name, basepath and description - √

Features (in-wishlist)

- Generate package type - like proxy, sharedflow etc.
- Proxy Name convention - postfix version in proxy name, e.g. hello-world-v1
- API First Approach - generate proxy bundle/resource-flow based on Open Specification 2.0/3.0

## Prerequisite

1. Maven

## How to use it

1. Basic use
   - open a new terminal;
   - execute this command to generate proxy skeleton -
     `sh $ mvn archetype:generate -DarchetypeGroupId=io.github.bhatikuldeep -DarchetypeArtifactId=maven-archetype-apigee-proxy -DarchetypeVersion=1.3 -DgroupId=apigee -DartifactId=sample-apigee-proxy`
   - Above command will ask you to enter - `proxy_endpoint`, enter e.g. https://ORGNAME-ENV.apigee.net; where ORGNAME is your apigee org and ENV is the env where you wish to run your postman test after the deployment.
   - This step will create a proxy folder with name - "sample-apigee-proxy", see the `artifactId` argument in above command with `basepath` = "v2/hello-world", `environment` = "test", `description` = "Sample maven-archetype-apigee-proxy API Proxy"
2. Advanced use
   - Nothing fancy, you can provide below argument to create a proxy skeleton, such as;
     - `artifactId` (name of the proxy, required),
     - `basepath` (optional, default value = v2/hello-world ),
     - `environment` (optional, default value = test),
     - `description` (optional, default value = Sample maven-archetype-apigee-proxy API Proxy) and
     - `proxy_endpoint` (required = yes, no default value)
   - now run this command to generate proxy skeleton
     `bash $ mvn archetype:generate -DarchetypeGroupId=io.github.bhatikuldeep -DarchetypeArtifactId=maven-archetype-apigee-proxy -DarchetypeVersion=1.3 -DgroupId=apigee -DartifactId=sample-apigee-proxy -Dbasepath=v2/hello-world -Denvironment=test -Ddescription="Sample maven-archetype-apigee-proxy API Proxy" -Dproxy_endpoint=https://ORGNAME-ENV.apigee.net`
3. Deployment
   - step 2 will create a `sample-apigee-proxy` folder with apigee edge compatible directory structure;
   - `$ cd sample-apigee-proxy` (or name of the proxy you just created, go to that directory)
   - Use `README.md` file from `sample-apigee-proxy` directory (or name of the proxy you just created, go to that directory), which has detailed instruction. Since this project is used to generate proxy skeleton, it does not make sense to have deployment instruction for your generated proxy part of this `README.md`, however it is included in your generated proxy you just created, so when you also check-in to separate git repo, your proxy readme is also part of it and can be referenced for later use;

## Issues, questions and feedback

https://github.com/bhatikuldeep/maven-archetype-apigee-proxy/issues
