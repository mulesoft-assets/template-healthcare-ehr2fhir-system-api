# Template Healthcare EHR System API

+ [License Agreement](#licenseagreement)
+ [Use Case](#usecase)
+ [Considerations](#considerations)
	* [Cloudhub security considerations](#cloudhubsecurityconsiderations)
	* [APIs security considerations](#apissecurityconsiderations)
+ [Run it!](#runit)
	* [Running on premise](#runonopremise)
	* [Running on Studio](#runonstudio)
	* [Running on Mule ESB stand alone](#runonmuleesbstandalone)
	* [Running on CloudHub](#runoncloudhub)
	* [Deploying your Anypoint Template on CloudHub](#deployingyouranypointtemplateoncloudhub)
	* [Creating externally reachable proxy and applying policies](#proxy)
	* [Properties to be configured (With examples)](#propertiestobeconfigured)

# License Agreement <a name="licenseagreement"/>
Note that using this template is subject to the conditions of this [License Agreement](AnypointTemplateLicense.pdf).
Please review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with Mule ESB Enterprise Edition, CloudHub, or as a trial in Anypoint Studio.

# Use Case <a name="usecase"/>

As a user of Healthcare API Led Connectivity Web Portal I want a microservice to act as a system API to provide services to upper layers of the architecture. 
This include creation, modification and retrieval of medical data from an EHR system.

EHR System API is part of the Healthcare Templates Solution and uses the standardized FHIR structures [version 1.0.2 DSTU2](https://www.hl7.org/FHIR/DSTU2/index.html).

The API is defined using [RAML 1.0](http://raml.org/) to provide type information for validation of requests and to help with the data transformation during development by providing useful metadata.


The following FHIR objects and operations are implemented in this API:

 + **AllergyIntolerance** - search, update, create
 + **Appointment** - search, create
 + **Condition** - search, update, create
 + **Patient** - search, read, update, create
 + **Practitioner** - search, read, update, create
 + **Schedule** - search, create
 + **Slot** - search, read, update, create

# Considerations <a name="considerations"/>

To run this Anypoint Template, there are certain preconditions that must be considered. **Failing to do so could lead to unexpected behavior of the template.**
This template uses SOAP services defined by WSDL files located at src/main/resources/wsdl folder.


### Running the application


# Run it! <a name="runit"/>
Simple steps to get Healthcare EHR System API running.
See below.

## Running on premise <a name="runonopremise"/>
In this section we detail the way you should run your Anypoint Template on your computer.


### Where to Download Mule Studio and Mule ESB
First thing to know if you are a newcomer to Mule is where to get the tools.

+ You can download Anypoint Studio from this [Location](http://www.mulesoft.com/platform/studio)
+ You can download Mule ESB from this [Location](http://www.mulesoft.com/platform/soa/mule-esb-open-source-esb)

### Importing an Anypoint Template into Studio
Anypoint Studio offers several ways to import a project into the workspace, for instance: 

+ Anypoint Studio Project from File System
+ Packaged mule application (.jar)

### Running on Studio <a name="runonstudio"/>
Once you have imported you Anypoint Template into Anypoint Studio you need to follow these steps to run it:

+ Locate the properties file `mule.dev.properties`, in src/main/resources
+ Complete all the properties required as per the examples in the section [Properties to be configured](#propertiestobeconfigured)
+ Once that is done, right click on you Anypoint Template project folder 
+ Hover you mouse over `"Run as"`
+ Click on  `"Mule Application"`

### Running on Mule ESB stand alone <a name="runonmuleesbstandalone"/>
Fill in all the properties in one of the property files, for example in [mule.prod.properties](../master/src/main/resources/mule.prod.properties) and run your app with the corresponding environment variable to use it. To follow the example, this will be `mule.env=prod`.

## Running on CloudHub <a name="runoncloudhub"/>
While [creating your application on CloudHub](https://docs.mulesoft.com/runtime-manager/hello-world-on-cloudhub) (Or you can do it later as a next step), you need to go to `"Manage Application"` > `"Properties"` to set all environment variables detailed in **Properties to be configured**.
Follow other steps defined [here](#runonpremise) and once your app is all set and started, there is no need to do anything else.

### Deploying your Anypoint Template on CloudHub <a name="deployingyouranypointtemplateoncloudhub"/>
Anypoint Studio provides you with really easy way to deploy your Template directly to CloudHub, for the specific steps to do so please check this [link](https://docs.mulesoft.com/anypoint-studio/v/7.1/deploy-mule-application-task#deploy-to-the-anypoint-platform)

## Properties to be configured (With examples) <a name="propertiestobeconfigured"/>
In order to use this Mule Anypoint Template you need to configure properties (APIs, Credentials, API Autodiscovery, etc.) either in properties file or in CloudHub as Environment Variables. Detail list with examples:
### Application properties

+ http.port `8081`

+ allergyintolerance.service `AllergyService`
+ allergyintolerance.port `AllergyServicePort`
+ allergyintolerance.address `http://example.com/allergyService`

+ appointment.service `AppointmentService`
+ appointment.port `AppointmentServicePort`
+ appointment.address `http://example.com/appointmentService`

+ condition.service `ConditionService`
+ condition.port `ConditionServicePort`
+ condition.address `http://example.com/conditionService`

+ patient.service `PatientService`
+ patient.port `PatientServicePort`
+ patient.address `http://example.com/patientService`

+ practitioner.service `PractitionerService`
+ practitioner.port `PractitionerServicePort`
+ practitioner.address `http://example.com/practitionerService`

+ schedule.service `ScheduleService`
+ schedule.port `ScheduleServicePort`
+ schedule.address `http://example.com/scheduleService`

+ slot.service `SlotService`
+ slot.port `SlotServicePort`
+ slot.address `http://example.com/slotService`
