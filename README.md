[![Build Status](https://travis-ci.com/abixen/abixen-platform.svg?branch=master)](https://travis-ci.com/abixen/abixen-platform)

# What is Abixen Platform

## Short introduce
Abixen Platform is a microservices based software platform for building enterprise applications. 
The main goal of the project is a creation of functionalities through creating particular microservices and integrating by provided CMS.

All you have to do in order to create an entirely new functionality is to implement a new, separated microservice.
Now you can register it in Abixen Platform and start using by delivered configuration wizards and CMS.
There is also an Abixen Platform API, which allows you to accelerate the process of new microservices creation.

A sample application built using Abixen Platform can look like in the following screenshot:
![Abixen Platform Demo](documentation-image/abixen-platform-demo.png "Abixen Platform Demo")


Abixen Platform's organizational division consists of pages and modules. 
User with appropriate privileges can create any page and select a layout. 
Finally, add to the page instances of modules deployed on Abixen Platform. 
Each of the modules can have many instances, configured by different parameters.

One of the most important mechanisms built-in into Abixen Platform is own security system, which
ensures a full control access to pages, modules and even the data displayed and used by the modules.
		
Abixen Platform delivers out of the box functional microservices. 
		
**Business Intelligence Service is one of the delivered functional modules.**

This module allows to do reporting charts and tables. A business administrator can create the charts and feed it by a following flow:
* Create a database connection to one of supported databases (H2, MySQL, PostgreSQL, Oracle, MSSQL). Instead of database connection, there is an opportunity to use an excel or CSV file
* Create a data source using above database connection or file.
* Add a new business intelligence instance on a page
* Configure a chart series selecting a data source
* Set permissions for particular users' roles

**Web Content Service is another one of the delivered functional modules.**

This module allows to do articles. A business administrator can create articles in two ways:
* Simple Web Content (just fill out a simple form with rich text editor)
* Advanced Web Content (using structures and templates)
		
The spectrum of possible modules developer can create is unlimited. 
There can be e.g. modules showing data in a tabular way, modules of data entry, 
where users enter data, edit and present.
		
The main architectural emphasis was placed on the rapid creation of new modules. 
Therefore, an original architecture has been implemented based on microservices, which
allows to create modules functionally independent of the other elements. 
When programmer creates a module, compiles only his module and his microservice. 
This provides a tremendous time saving comparing to monolithic systems.

## Technology stack
![Abixen Platform Microservices Technology Stack](documentation-image/abixen-platform-microservices-technology-stack.png "Abixen Platform Microservices Technology Stack")

## Architecture overview
One of the biggest advantage is the architecture based on microservices concept. 
With loosely coupled components, it opens up a possibility of a efficient division of work between development teams and for a simple and inexpensive system maintenance.
Creating a new module, a new functionality, a developer must not interfere with the existing source code. He can create a new microservice, being a separate spring boot application. 
Then, implementing necessary interfaces achieves opportunity to integrate the newly created microservice with Abixen Platform structure.
Finally, a business administrator may use it over the platform.
Abixen Platform supplies out of the box a few functional modules closed in the Business Intelligence Service and in the Web Content Service.
This is a good example, how to create the own microservice.
Mentioned services provide mainly visualisation functionalities, such as charts, micro charts, KPIs. As well as a web content management, such as templates, structures, articles.
However opportunities to develop data entry modules are still opened!
![Abixen Platform Microservices Architecture](documentation-image/abixen-platform-microservices-architecture.png "Abixen Platform Microservices Architecture")

## AWS compatible
Abixen Platform is fully compatible with AWS cloud and utilizes the following services:

   * **EC2** - used as a base for hosts running docker in ECS Cluster
   * **ALB** - modern version of load balancer aligned with microservices architecture topology
   * **ECS** - container orchestrator and scheduler for all services running as docker containers
   * **ECR** - private container registry for docker images
   * **Route53** - allows to use internal dns names for communication between microservices
   * **CloudWatch** - used as a central monitoring and logging
   * **Elasticache** - used internally by Abixen Platform components
   * **RDS** - database store for all components
   * **SES** - used for email communication
   
![Abixen Platform AWS Deployment diagram](documentation-image/abixen-platform-on-aws.png "Abixen Platform AWS Deployment diagram")

## Logging and monitoring
All containers from Abixen Platform send logs to [Elasticsearch](https://www.elastic.co) via [Logstash](https://www.elastic.co/products/logstash). You can use [Kibana's](https://www.elastic.co/products/kibana) interface as well.
All metrics are exposed on each component with [Jolokia](http://jolokia.org) and fetched from there using [Telegraf](https://influxdata.com/telegraf-correlate-log-metrics-data-performance-bottlenecks/). They are sent to [InfluxDB](https://influxdata.com/) and are accessible on [Grafana](https://grafana.net) dashboards
![Abixen Platform Logging and Monitoring](documentation-image/abixen-docker-infrastructure.png "Abixen Platform Logging and Monitoring")

# History

Abixen Platform has been started in March 2015 by Mariusz Kumor (<a href="https://www.linkedin.com/in/mariuszkumor">see LinkedIn profile</a>). 
Preliminary the main idea was to learn more about microservices, 
Spring Cloud stuff and extend knowledge about AngularJS.
The project was developing to December 2015 at free time.
Substantial part of the time involved analysis and prototypes. 
Since that day it took some time but now, 
in October 2016 he decided to publish the source code on GitHub. 
As well Mariusz Kumor decided to begin further development.
The great motivation were flattering words of his friends, 
also some companies about the project and its ideas.

# Give a Star ⭐
Creating this product I put emphasis primarily on quality and value for end users. It is also very important for me that the software is built based on the cutting-edge technologies (but in the same time stable ones) and the best design patterns and practices. As you can guess, it takes a lot of time, and the product is open source - so everyone can use the effects of my and other Contributors work for free. If you like this project, learned something or you are using it, please give it a star ⭐. This is the best motivation for me to continue on. Thank you!

# Share It
There are not many similar open source products like this type of application. If in your opinion this repository makes a difference and deserves it - please share it with your friends, mates and on social networks. I will be very grateful.

# Known issues

There are some known issues. We work on fixes and improvements.

* Not all translations are done
* Multi Visualisation Service needs some user interface improvement and optimization. Also needs more tests.
* In some places CSS is not perfect
* There is a small technical debt (non functional issue)

# Get it started
The documentation is available under https://github.com/abixen/abixen-platform/wiki page.

# We are looking for experienced Contributors
Are you good at Java and / or frontend technologies like AngularJS, CSS, HTML?
Or maybe are you an UI/UX expert and you are willing to enhance Abixen Platform's design?
Would you like to join geek guys? 
If so, we are ready to do short but powerful training for you from Abixen Platform.
After the training you will be able to develop together with us the amazing Abixen Platform.
Just mail us **info@platform.abixen.com**. In a message please let us know, why would you like to contribute and what could you bring to the project.

# [How to contribute to the repository](CONTRIBUTING.md)

# License

Copyright (c) 2010-present Abixen Systems. All rights reserved.
 
This library is free software; you can redistribute it and/or modify it under
the terms of the GNU Lesser General Public License as published by the Free
Software Foundation; either version 2.1 of the License, or (at your option)
any later version.

This library is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more
details.