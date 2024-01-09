# Setting Up Appium on Windows and Tools You Need To Start Automate a Test

Hi everyone that is reading this documentation! My name is Hansen Tandi, by reading this documentation I'm sure that you're really interested in trying to automate a testing for mobile app, but you are wondering "Where do I start?", From that question arised, is the motivation for me to create this documentation for beginners like me to make have you set up your appium on your windows (This guide does not contain any installation guide on Mac, but the steps are fairly similiar).

## Step by Step Things To Install
**1.NodeJS**

You can directly go to the download page website of [NodeJS](https://nodejs.org/en/download) and download the latest for windows version. 

**2.Appium**

After downloading and installing NodeJS, you can start on installing Appium using npm. Firstly open your command prompt and input these command.

```bash
npm i -g appium
```

You can check the installed Appium version by running this command.

```bash
appium -v
```

After the installation is finished, you can type these command to the command prompt.

```bash
appium-installer
```

The output should be something like this.

```bash

👋 Hello, Appium user ✨

? Select an option (Use arrow keys)
> Need help setting up Android Environment to run your Appium test?
  Need help setting up iOS Environment to run your Appium test?
  Install Appium Server
  Install Appium Drivers
  Install Appium Plugin
  Run Appium Doctor
  Launch Emulators/Simulators
(Move up and down to reveal more choices)

```

This command will help you according to what you need, for example you can check how to setting the Android Environment as well as the iOS Environment, you can start selecting the options by moving your up and down arrow key, after that just press ```ENTER```. In our case right now, because we are using Windows, our goal is to install the Android version. So first of all, you can start by selecting the ```Need help setting up Android Environment to run your Appium test?``` command. The output should be something like this.

```bash
? Select target device(s): (Use arrow keys)
> Real Android Device
  Android Emulator
  Both
```

You can select according to what you needed, but for now we'll stick with the ```Both``` option. After this, the output should be something like this.

```bash
? [Emulator] Select browser(s) to set up on Emulator: (Use arrow keys)
> Google Chrome
  Mozilla Firefox
  Both
  None
```

For this option is also according to what you need to automate, you can select ```None``` option if you will not be automating any browsers. After this it will check any missing binaries and will attempt to complete the setup. The output should be like this.

```bash
? Do you wish to download the missing binaries and complete setup? (Use arrow keys)
> Yes
  Not now
```

You can try to select 'Yes' for now. After this, start on selecting the ```Install Appium Server``` option to install the **Appium Server**.

**3.Drivers**

To automate a test, Drivers is an important component, Drivers are component that allows you to interface with the mobile device and application. In this case because we are setting up the Android environment, we will have to install the driver that supports Android, in this case it will be the ```uiautomator2``` for Android. To install the driver you can start selecting the ```Install Appium Drivers``` option. The output should be something like this.

```bash
- Fetching available official drivers{
    "uiautomator2": {
        "pkgName": "appium-uiautomator2-driver",
        "version": "2.37.0",
        "installType": "npm",
        "installSpec": "uiautomator2",
        "installPath": "C:\\Users\\Hansen\\.appium\\node_modules\\appium-uiautomator2-driver",
        "appiumVersion": "^2.0.0",
        "automationName": "UiAutomator2",
        "platformNames": [
            "Android"
        ],
        "mainClass": "AndroidUiautomator2Driver",
        "scripts": {
            "reset": "scripts/reset.js"
        },
        "installed": true
    },
    "xcuitest": {
        "pkgName": "appium-xcuitest-driver",
        "version": "5.12.2",
        "installType": "npm",
        "installSpec": "xcuitest",
        "installPath": "C:\\Users\\Hansen\\.appium\\node_modules\\appium-xcuitest-driver",
        "appiumVersion": "^2.0.0",
        "automationName": "XCUITest",
        "platformNames": [
            "iOS",
            "tvOS"
        ],
        "mainClass": "XCUITestDriver",
        "scripts": {
            "build-wda": "./scripts/build-wda.js",
            "open-wda": "./scripts/open-wda.js"
        },
        "schema": {
            "$schema": "http://json-schema.org/draft-07/schema",
            "type": "object",
            "properties": {
                "webdriveragent-port": {
                    "appiumCliDest": "wdaLocalPort",
                    "default": 8100,
                    "description": "Local port used for communication with WebDriverAgent",
                    "maximum": 65535,
                    "minimum": 1,
                    "type": "integer"
                }
            },
            "additionalProperties": false,
            "title": "XCUITest Driver Configuration",
            "description": "Appium configuration schema for the XCUITest driver.",
            "$id": "driver-xcuitest.json"
        },
        "installed": true
    },
    "mac2": {
        "pkgName": "appium-mac2-driver",
        "installed": false
    },
    "espresso": {
        "pkgName": "appium-espresso-driver",
        "installed": false
    },
    "safari": {
        "pkgName": "appium-safari-driver",
        "installed": false
    },
    "gecko": {
        "pkgName": "appium-geckodriver",
        "installed": false
    },
    "chromium": {
        "pkgName": "appium-chromium-driver",
        "installed": false
    }
}
√ Fetching available official drivers
? Select Drivers to install (Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to
proceed)
>( ) uiautomator2
 ( ) xcuitest
 ( ) mac2
 ( ) espresso
 ( ) safari
 ( ) gecko
 ( ) chromium
```

Select the ```>( ) uiautomator2``` option and press ```ENTER``` and wait for the process to finish.

**Notes**
You can also install Appium Plugins from ```appium-installer``` and I highly recommend for you to install the ```appium-wait-plugin```, this plugin will help to automatically wait for an element to appear, so in the future you would not have to set any wait at your scripts.

**4.Starting Appium Server**

After all those setups, you can try to start the Appium server, just type ```appium``` in the command prompt and press ```ENTER```. The output should be something like this.

```bash
[Appium] Welcome to Appium v2.3.0
[Appium] The autodetected Appium home path: C:\Users\Hansen\.appium
[Appium] Attempting to load driver uiautomator2...
[Appium] Attempting to load driver xcuitest...
[Appium] Requiring driver at C:\Users\Hansen\.appium\node_modules\appium-uiautomator2-driver\build\index.js
[Appium] Requiring driver at C:\Users\Hansen\.appium\node_modules\appium-xcuitest-driver\build\index.js
[Appium] AndroidUiautomator2Driver has been successfully loaded in 2.043s
[Appium] XCUITestDriver has been successfully loaded in 2.043s
[Appium] Appium REST http interface listener started on http://0.0.0.0:4723
[Appium] You can provide the following URLs in your client code to connect to this server:
[Appium]        http://192.168.0.100:4723/
[Appium]        http://127.0.0.1:4723/ (only accessible from the same host)
[Appium] Available drivers:
[Appium]   - uiautomator2@2.37.0 (automationName 'UiAutomator2')
[Appium]   - xcuitest@5.12.2 (automationName 'XCUITest')
[Appium] Available plugins:
[Appium]   - appium-dashboard@v2.0.2
[Appium]   - element-wait@3.0.0
[Appium] No plugins activated. Use the --use-plugins flag with names of plugins to activate
```

Congratulations! Appium is now installed and running in your Windows, but we are not done yet. From these information, you can tell what drivers and plugins that are installed and many more other information.

**5.Appium Inspector**

Appium Inspector is an important component to automate a test. Appium Inspector is a graphical user interface (GUI) tool that are used to inspect and interact with an element on mobile applications. You can start downloading Appium Inspector [here](https://github.com/appium/appium-inspector/releases) then select the windows version and start installing.

**6.IDE (IntelliJ Community Edition)
To start an automation test, you will need an IDE (Integrated Development Environment) to create a script. For this documentation, I will use IntelliJ, you can also try to use Visual Studio Code or any other IDE that pique your interest more. You can download IntelliJ [here](https://www.jetbrains.com/idea/download/).

**7.Java Client**

For this guide I will be using Java to create an automation scripts, Because we will use Java to create an automation scripts we will need to apply the Java Client to the project as well.

You can start by adding the following to pom.xml:
```bash
<dependency>
  <groupId>io.appium</groupId>
  <artifactId>java-client</artifactId>
  <version>${version.you.require}</version>
  <scope>test</scope>
</dependency>
```

**Make sure that you have installed Java JDK in your windows, if not you can start downloading it from [here](https://www.oracle.com/java/technologies/downloads/)**

**8.Virtual Device**

Next we will have to set a device to run our application. The easiest way to do this is by downloading and installing the Android Studio, and download a virtual device from there. You can download it from [here](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChcSEwjV2p_ozNCDAxVjpWYCHZHPCxUYABAAGgJzbQ&ase=2&gclid=CjwKCAiA-vOsBhAAEiwAIWR0TcT3B5Hb09DMaArnKtSev5G8LmbiNFp8dMl2RBSGHFOVgCdSr-lLgRoCc4IQAvD_BwE&ohost=www.google.com&cid=CAESVuD2_BmXTGSUwcasKvYOfU8UmvOVvw7Qwwte-bVoTeKzmmrjOymVj_FeOgo98OtN3NrW9b5_q0Imk4l6emm1ElpCBsUarHoCgODqdETHKEdnAIl3BfDL&sig=AOD64_17PAZZ9-6G-v5cP7kggV_n2AMeeQ&q&nis=4&adurl&ved=2ahUKEwiDqZnozNCDAxVP-zgGHSY8AGkQ0Qx6BAgIEAE). After installing it you can start to setup the android SDK and continue to set a AVD manager from Android Studio. From there you can select your prefered device, after selecting it select the OS, and voila! you have a virtual device installed!

That is all folks! If you have all these components installed you can start scripting to automate a test using Java! I hope that by making this documentation, it could help more people to start mobile automation testing smoothly. Thank you for reading this documentation!














