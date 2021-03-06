# NEBA Directive: a sample application for the NEBA framework for Apache Sling
This project demonstrates core concepts and features of the NEBA framework for Sling. 
It provides a demonstrative mini WEB application for the beautiful responsive _directive_ template set by [http://html5up.net](http://html5up.net).

![NEBA Directive: A sample application for NEBA for Sling](README/intro.png)

## What this sample application is
This application demonstrates how NEBA can be used to model resources in Sling and use Spring's MVC features for Apache Sling.

## What this sample application is _not_ 
A ready-to-use web application. It has purely been designed to demonstrate NEBA features.
 
## How to run this application
1. Build the Neba Sample bundle in the root directory with `mvn install`
2. Build the Neba Sample Launchpad in the launchpad directory with `mvn install`
3. Start your Neba Sample Launchpad in the launchpad directory with `mvn slingstart:start` (Can be stopped again by pressing any key)
5. Open [http://localhost:8080/content/neba-sample.html](http://localhost:8080/content/neba-sample.html) or browse NEBA's 
   [Model registry](http://localhost:8080/system/console/modelregistry),[Model statistics](http://localhost:8080/system/console/modelstatistics) or examine logfiles using NEBA's [log viewer](http://localhost:8080/system/console/logviewer).
6. You may login with any sling user, e.g. using admin/admin for the default administrative account.
7. To configure the SMTP settings for the contact form, see /system/console/configMgr, "io.neba.sample.mail" and "NEBA sample project contact email sender".
 
## The anatomy of this app
The NEBA sample app is an OSGi bundle. It contains application code (Java POJOs, Services annotated with SCR metadata, NEBA models) in the "to.adapt.neba" package.

The bundle is [blueprint-enabled](http://www.eclipse.org/gemini/blueprint/) as it provides a blueprint context xml file in OSGI-INF/blueprint.

In addition, the bundle provides JCR content, views, images and configurations via [Sling content loading](https://sling.apache.org/documentation/bundles/content-loading-jcr-contentloader.html).
The respective content is contained in the SLING-INF/content folder and is loaded into the repository as specified by the `Sling-Initial-Content` header values defined in the pom.xml.

Furthermore, the bundle directly [provides static resources](https://sling.apache.org/documentation/bundles/bundle-resources-extensions-bundleresource.html) via the `Sling-Bundle-Resources` header value defined in the pom.xml. 