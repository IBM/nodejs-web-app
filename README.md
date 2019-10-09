<p align="center">
    <a href="https://cloud.ibm.com">
        <img src="https://landscape.cncf.io/logos/ibm-cloud-kcsp.svg" height="100" alt="IBM Cloud">
    </a>
</p>


<p align="center">
    <a href="https://cloud.ibm.com">
    <img src="https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg" alt="IBM Cloud">
    </a>
    <img src="https://img.shields.io/badge/platform-node-lightgrey.svg?style=flat" alt="platform">
    <img src="https://img.shields.io/badge/license-Apache2-blue.svg?style=flat" alt="Apache 2">
</p>


# Create and deploy a Node.js web application

> We have similar applications available for [Go](https://github.com/IBM/go-web-app), [Java Spring](https://github.com/IBM/spring-web-app), [Swift](https://github.com/IBM/swift-web-app), Python [Django](https://github.com/IBM/django-web-app) & [Flask](https://github.com/IBM/flask-web-app), and [Java Liberty](https://github.com/IBM/java-liberty-web-app).

In this sample application, you will create a web application using Express to serve web pages in Node.js, complete with standard best practices, including a health check and application metric monitoring.

This app contains an opinionated set of files for web serving:

- `public/index.html`
- `public/404.html`
- `public/500.html`


## Steps

You can [deploy this application to IBM Cloud](https://cloud.ibm.com/developer/appservice/create-app?starterKit=ab2263e9-c787-32e6-a9d7-298c20557bbb) or [build it locally](#building-locally) by cloning this repo first. Once your app is live, you can access the `/health` endpoint to build out your cloud native application.

### Deploying to IBM Cloud

<p align="center">
    <a href="https://cloud.ibm.com/developer/appservice/create-app?starterKit=ab2263e9-c787-32e6-a9d7-298c20557bbb">
    <img src="https://cloud.ibm.com/devops/setup/deploy/button_x2.png" alt="Deploy to IBM Cloud">
    </a>
</p>

Use the button above to deploy this same application to IBM Cloud. This option will create a deployment pipeline, complete with a hosted Git lab project and DevOps toolchain. You will have the option of deploying to either Cloud Foundry or a Kubernetes cluster. [IBM Cloud DevOps](https://www.ibm.com/cloud/devops) services provides toolchains as a set of tool integrations that support development, deployment, and operations tasks inside IBM Cloud. 


### Building Locally

To get started building this application locally, you can either run the application natively or use the [IBM Cloud Developer Tools](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started) for containerization and easy deployment to IBM Cloud.

#### Native Application Development

- Install the latest [Node.js](https://nodejs.org/en/download/) 10+ LTS version.

Once the Node toolchain has been installed, you can download the project dependencies with:

```bash
npm install
```

To run your application locally:

```bash
npm run start
```

Your application will be running at `http://localhost:3000`. You can access the `/health` endpoint at the host.

#### IBM Cloud Developer Tools

Install [IBM Cloud Developer Tools](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started) on your machine by running the following command:
```
curl -sL https://ibm.biz/idt-installer | bash
```

Create an application on IBM Cloud by running:

```bash
ibmcloud dev create
```

This will create and download a starter application with the necessary files needed for local development and deployment.

Your application will be compiled with Docker containers. To compile and run your app, run:

```bash
ibmcloud dev build
ibmcloud dev run
```

This will launch your application locally. When you are ready to deploy to IBM Cloud on Cloud Foundry or Kubernetes, run one of the following commands:

```bash
ibmcloud dev deploy -t buildpack // to Cloud Foundry
ibmcloud dev deploy -t container // to K8s cluster
```

You can build and debug your app locally with:

```bash
ibmcloud dev build --debug
ibmcloud dev debug
```

##### Session Store

You may see this warning when running `ibmcloud dev run`:
```
Warning: connect.session() MemoryStore is not
designed for a production environment, as it will leak
memory, and will not scale past a single process.
```

When deploying to production, it is best practice to configure sessions to be stored in an external persistence service.

## Next Steps
* Learn more about augmenting your Node.js applications on IBM Cloud with the [Node Programming Guide](https://cloud.ibm.com/docs/node?topic=nodejs-getting-started).
* Explore other [sample applications](https://cloud.ibm.com/developer/appservice/starter-kits) on IBM Cloud.

## License

This sample application is licensed under the Apache License, Version 2. Separate third-party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1](https://developercertificate.org/) and the [Apache License, Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache License FAQ](https://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)
