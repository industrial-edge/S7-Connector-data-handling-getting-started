# Configuration

- [Configuration](#configuration)
  - [Configure PLC Connection](#configure-plc-connection)
    - [Configure the Databus](#configure-the-databus)
    - [Configure the SIMATIC S7 Connector](#configure-the-simatic-s7-connector)
  - [Configure Flow Creator](#configure-flow-creator)

## Configure PLC Connection

To read data from the PLC and provide the data, we will use the SIMATIC S7 Connector to establish connection with the PLC via S7.

The SIMATIC S7 sends the data to the Databus, where the Flow Creator app can collect what is needed.

In order to build this infrastructure, these apps must be configured properly:

- Databus
- SIMATIC S7 Connector

### Configure the Databus

In your IEM open the Databus and launch the configurator.

Add a user with this topic:
`"ie/#"`

![IE_Databus_User.png](graphics/IE_Databus_User.png)

![ie_databus](graphics/IE_Databus.png)

Deploy the configuration.

### Configure the SIMATIC S7 Connector 

Simatic S7 Connector can be configured via both bellow mentioned options


###### a) Local configuration with Industrial edge device

###### b) Central configuration with Industrial edge managment 


#### Local Configuration

In your Industrial edge device open the common configurator and configure the S7 connector

This Configuration done localy at the Industrial edge Device

Add a data source:

![S7_data_source](graphics/S7_data_source.png)

Add a data Databus credentials in common configurator:

![Databus_IIH.PNG](graphics/Databus_IIH.PNG)

Hint: Username and password should be the same as was set in the Databus configuration, e.g., "edge" / "edge".

Deploy and start the project.

Import the tags to S7 connector from S7.zip file exported from TIA portal by using export SCADA simatic tool in common configurator:

![Importtags1.PNG](graphics/Importtags1.PNG)

Add these four tags GDB.signals.tankSignals.actLevel, GDB.signals.tanksignals.actTemperature, GDB.signals.bottleSignals.maxLevel, GDB.signals.energySignals.energyConsumptionfillingtank with 1 sec of acquisition cycle (since we want to write variable values into the PLC, set "Read & Write" as access mode): 

![s7tags1.PNG](graphics/s7tags1.PNG)

>Hint! Please use the same variable names as shown in the screenshot, otherwise the flow creator script must be adjusted.

#### Central Configuration

In your IEM open the SIMATIC S7 Connector and launch the configurator.

This configuartion done centraly at IEM 

Add a data source:

![S7_datasource.png](graphics/S7_datasource.png)

Browse the tags from the PLC 
![s7centraltags](graphics/s7centraltags.PNG)

Add these four tags GDB.signals.tankSignals.actLevel, GDB.signals.tanksignals.actTemperature, GDB.signals.bottleSignals.maxLevel, GDB.signals.energySignals.energyConsumptionfillingtank with 1 sec of acquisition cycle (since we want to write variable values into the PLC, set "Read & Write" as access mode):  

Edit the settings:

![s7_connector_settings](graphics/S7_Connector_Settings.png)

Hint: Username and password should be the same as was set in the Databus configuration, e.g., "edge" / "edge".


## Configure Flow Creator

Open the Flow Creator App from the IED Web UI and import the [FlowCreator.JSON](../src/FlowCreator.json) file from the source folder.

![importFlowCreator.PNG](graphics/importFlowCreator.PNG)

![importFlow2.PNG](graphics/importFlow2.PNG)

After importing the JSON file, the password set in the Databus must be entered in the security settings of the MQTT-node.

![ServerEinstellungen.PNG](graphics/Server_einstellungen.PNG)

![SecuritySetting.PNG](graphics/SecuritySetting.PNG)



