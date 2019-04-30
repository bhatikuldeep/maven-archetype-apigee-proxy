

# Apigee Edge - Proxy Template Generator (with maven archtype)
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
### Using this repo as local maven repository;       
1. Clone this repo
    `$ git clone https://github.com/bhatikuldeep/maven-archetype-apigee-proxy.git`
2. `$ cd maven-archetype-apigee-proxy`
3. Install this archtype locally- `$ mvn clean install`
4. Generate the proxy bundle    
    - for Basic use;
        - open a new terminal;
        - `$ cd ..`
        - now run this command to generate proxy skeleton 
        ``` bash $ mvn archetype:generate -DarchetypeGroupId=apigee-proxy-groupId -DarchetypeArtifactId=maven-archetype-apigee-proxy -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=apigee -DartifactId=sample-apigee-proxy```    
    - for Advanced use;
        -  additional supported options are 
            - `proxyname` (optional, default value = sample-apigee-proxy), 
            - `basepath` (optional, default value = v2/hello-world ), 
            - `environment` (optional, default value = test), 
            - `description` (optional, default value = Sample maven-archetype-apigee-proxy API Proxy) and 
            - `proxy_endpoint` (requried = yes, no default value)
        -  now run this command to generate proxy skeleton 
            ``` bash $ mvn archetype:generate -DarchetypeGroupId=apigee-proxy-groupId -DarchetypeArtifactId=maven-archetype-apigee-proxy -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=apigee -DartifactId=sample-apigee-proxy -Dproxyname=sample-apigee-proxy -Dbasepath=v2/hello-world -Denvironment=test -Ddescription="Sample maven-archetype-apigee-proxy API Proxy" -Dproxy_endpoint=https://yourorgname-yourenv.apigee.net```
5. Deployment 
    - step 4 will create a `sample-apigee-proxy` folder with apigee edge compatible directory structure;
    - for deployment use `README.md` file from `sample-apigee-proxy` direcotry, which has detailed instruction. Since this project is used to generate proxy skeleton, it does not make sense to have deployment instruction part of this `README.md`, instead it is included in just generated proxy you just created.
            
### Using Maven Central Repo - Todo

## Issues, questions and feedback
https://github.com/bhatikuldeep/maven-archetype-apigee-proxy/issues
