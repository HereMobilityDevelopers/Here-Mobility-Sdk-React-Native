# HERE Mobility React Native SDK

## Introduction ##

HERE Mobility offers a mobility platform solution to transportation service providers, businesses, and consumers. The platform consists of the HERE Mobility Marketplace and SDK packages.

The HERE Mobility Marketplace is a "broker" between transportation suppliers and consumers, which matches up ride requests with ride offers. Using the HERE Mobility SDK, you can enable your users to book and manage ride services within your app.

The HERE Mobility React Native SDK allows you to add HERE Mobility features to your app using the React Native framework. This allows you to develop your app in Javascript, and compile it for either the iOS or Android environments.

## Install the SDK with npm

To install the HERE Mobility React Native SDK using the **npm** package manager, run the following command:

`$ npm install react-native-here-mobility-sdk --save`


## Link the SDK to your project

### Automatic linkage with npm

To link the SDK to your project using the **npm** package manager, run the following commands:

```bash
$ npm i -g react-native-cli
$ react-native link react-native-here-mobility-sdk
```

### Manual linkage

#### iOS

To link the SDK to your project manually in an iOS environment:

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`.
2. Go to `node_modules` ➜ `react-native-here-mobility-sdk` and add `RNHereMobilitySdk.xcodeproj`.
3. In XCode, in the project navigator, select your project. Add `libRNHereMobilitySdk.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`.

#### Android

To link the SDK to your project manually in an Android environment:

1. Open the file `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import here.mobility.sdk.RNHereMobilitySdkPackage;` to the imports at the beginning of the file.
  - Add `new RNHereMobilitySdkPackage()` to the list returned by the `getPackages()` method.
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-here-mobility-sdk'
  	project(':react-native-here-mobility-sdk').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-here-mobility-sdk/android')
  	```
3. Add the following line to the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-here-mobility-sdk')
  	```

## Configure and initialize HereMobilitySDK

#### iOS

>**Note**: **HereMobilitySDK** is a dynamic framework. To use it, you must specify ```use_frameworks!``` in your project's podfile.

To configure and initialize HereMobilitySDK in an iOS environment: 

1. Follow the instruction in the [HereMobilitySDK Installation Guide](https://github.com/HereMobilityDevelopers/Here-Mobility-SDK-iOS#2-pre-requisites)

2. Run the following command:

    ```bash
    $ cd (node_modules/react-native-here-mobility-sdk/ios && pod install)
    ```
3. Open your project's workspace; build and run your project.

#### Android 

To configure and initialize HereMobilitySDK in an Android environment: 

1. Open your project in Android Studio.

2. In your project’s root ```build.gradle```, add the following lines to your repositories section:

	```
	buildscript {
	    repositories {
			...
	 		maven {
	        	url 'https://maven.google.com/'
	            name 'Google'
	        }
		}
	}
	
	allprojects {
	    repositories {
			...
			maven {
				url "https://mobility.bintray.com/sdk"
			} 
	        maven {
	            url 'https://maven.google.com/'
	            name 'Google'
	        }
		}
	}
	```
3. Follow the instruction in the [HereMobilitySDK Installation Guide](https://github.com/HereMobilityDevelopers/HERE-Mobility-SDK-Android#prereqs), steps 3.i through 3.viii.

## Usage

To use the HERE Mobility SDK, add the following line to your app's Javascript code. Use the **HereMobilitySDKDemand** functions for ride booking and management.

```javascript

const { HereMobilitySDKDemand , HereMobilitySDK } = require("react-native-here-mobility-sdk");

```
  
