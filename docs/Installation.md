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

![S7_data_source.png](S7_data_source.png)

![ie_databus](graphics/IE_Databus.png)

Deploy the configuration.

### Configure the SIMATIC S7 Connector

In your IED open the common configuratort and configure the S7 connecotr 

Add a data source:

![S7_connector_data_source](graphics/S7_Connector_Data_Source.png)

Add needed tags (since we want to write variable values into the PLC, set "Read & Write" as access mode): 

![s7_connector_config](graphics/S7_Connector_Configuration.PNG)

>Hint! Please use the same variable names as shown in the screenshot, otherwise the flow creator script must be adjusted.

Edit the settings:

![s7_connector_settings](graphics/S7_Connector_Settings.png)

Hint: Username and password should be the same as was set in the Databus configuration, e.g., "edge" / "edge".

Deploy and start the project.

## Configure Flow Creator

Open the IE Flow Creator App from the IED Web UI and import the [FlowCreator.JSON](../src/FlowCreator.json) file from the source folder.

![importFlowCreator.PNG](graphics/importFlowCreator.PNG)

![importFlow2.PNG](graphics/importFlow2.PNG)

After importing the JSON file, the password set in the Databus must be entered in the security settings of the MQTT-node.

![ServerEinstellungen.PNG](graphics/Server_einstellungen.PNG)

![SecuritySetting.PNG](graphics/SecuritySetting.PNG)



