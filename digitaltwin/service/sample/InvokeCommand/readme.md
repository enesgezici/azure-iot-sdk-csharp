#  Invoke Command Sample

This sample demonstrates how to invoke a command onto a digital twin that is actively listening for commands

## How to run the sample

### Setup environment

This sample is a .NET Core 2.2 project, so to build and run this sample, 
your device must have the .NET Core 2.2 SDK installed. 

[Follow this link to download this SDK][netcore-sdk-download]

### Sample Arguments

In order to run this sample, you must set environment variables for:
- "IOTHUB_CONNECTION_STRING" - Your IoT Hub's connection string
- "DIGITAL_TWIN_ID" - Your digital twin id to invoke the command onto
- "INTERFACE_INSTANCE_NAME" - The interface the command belongs to
- "COMMAND_NAME" - The name of the command to invoke on your digital twin
- "PAYLOAD" - (optional) The Json payload to include in the command

### Other Prerequisites

In order to run this sample, you will need an IoT Hub. You will also need at least one device registered in this hub so that the sample can interact with that device
* [Setup Your IoT Hub][lnk-setup-iot-hub]

This device must also be registered to implement the interface whose command you want to invoke, and the device
must be online to receive the command invocation.

To see sample code that demonstrates how to register a device to implement an interface and to listen for commands, see the device sample [here](../../../device-samples)

### Run the sample

This sample can be run using either Visual Studio 2019 or from command line

To run this sample from commandline, run the following command from this folder:

```sh
dotnet run
```

This will build the necessary Nuget packages and run the sample for you

The sample will invoke the configured command on the listening device, print out the result, and then exit.

The command response will depend on how the device is setup to respond to your command invocation, but an example response is below:

```sh
Command someCommand invoked on the device successfully, the returned status was 200 and the request id was 0b7ff5f4-6245-4c6b-a891-f2d3dc802a41
The returned payload was
{"someKey" : "someValue"}
```

[lnk-setup-iot-hub]: https://aka.ms/howtocreateazureiothub
[netcore-sdk-download]: https://dotnet.microsoft.com/download/dotnet-core/2.2