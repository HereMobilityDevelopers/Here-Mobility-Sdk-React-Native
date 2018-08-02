# react-native-here-mobility-sdk

## Getting started

`$ npm install react-native-here-mobility-sdk --save`


## Link the project
### Mostly automatic installation

```bash
$ npm i -g react-native-cli
$ react-native link react-native-here-mobility-sdk
```

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-here-mobility-sdk` and add `RNHereMobilitySdk.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNHereMobilitySdk.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import here.mobility.sdk.RNHereMobilitySdkPackage;` to the imports at the top of the file
  - Add `new RNHereMobilitySdkPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-here-mobility-sdk'
  	project(':react-native-here-mobility-sdk').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-here-mobility-sdk/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-here-mobility-sdk')
  	```



## Install HereMobilitySDK

HereMobilitySDK is a dynamic framework.
Specifing 'use_frameworks!' in PodFile is mandatory for using HereMobilitySDK.

#### iOS

1. Follow after HereMobilitySDK [Installation guide](https://github.com/HereMobilityDevelopers/Here-Mobility-SDK-iOS#2-pre-requisites)

2. Add 'use_frameworks!' to project pod file.

3. In your main root diractory project run

```bash
$ (cd node_modules/react-native-here-mobility-sdk/ios && pod install) && (cd ios && pod install)
```
4. Open your workspace project and build and run.

#### Android
1. Open the project with android studio

2. In your project’s root build.gradle, add the following to your repositories section:

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
		maven{
			url "https://mobility.bintray.com/sdk"
		}
        maven {
            url 'https://maven.google.com/'
            name 'Google'
        }

	}
}
```
3. Follow after HereMobilitySDK [Installation guide](https://github.com/HereMobilityDevelopers/HERE-Mobility-SDK-Android#prereqs)

## Usage
```javascript

const { HereMobilitySDKDemand , HereMobilitySDK } = require("react-native-here-mobility-sdk");

```
