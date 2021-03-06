snow-import-plugin
==================

### ServiceNow import Plugin
This plugin imports CI and relations from the ServiceNow CMDB REST web service.

#### What is ServiceNow ?
ServiceNow is a Platform-As-A-Service (PAAS) solution of IT Service Management (ITSM).

### How to install or update it ?
Remove any exisiting org.archicontribs.servicenow*.jar from your Archi plugins folder.
Download the *org.archicontribs.servicenow_1.1.jar* file to your Archi 3 plugins folder or the *org.archicontribs.servicenow_1.1(archi4).jar* file to your Archi 4 plugins folder.
Download the servicenow.ini file to your local drive (like "My documents") and edit it to adapt it to your needs.

#### Use-cases
This plugin is useful when one wishes to import all the existing CIs from SericeNow and use Archi to describe the existing technical base.

#### How it works ?
An existing model must be created and selected. The "import from ServiceNow" option becomes available in the file/Import menu.

When ran, the plugin asks for an INI file that contains all the required options:
   - ServiceNow URL and credentials
   - Proxy information and credentials if any
   - Logging requirements (Log4j)
   - Mapping between the ServiceNow CIs and the Archi elements
   - Organization of the Arhi elements (folder names, properties, ...)
   - Mapping between the ServiceNow relations and the Archi relations
   - ...

The plugin connects to the ServiceNow web services, generates the REST request, download and parse the data. The request is optimised to reduce the quantity of data downloaded (only the fields described in the ini file are downloaded).

The plugin may be ran several times. Only the changes detected in ServiceNow since the last run will be applied to the Archi objects. A full log of what is done can be generated through Log4j.
