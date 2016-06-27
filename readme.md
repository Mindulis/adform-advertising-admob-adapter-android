# Introduction

The Adform Admob adapter can be used to integrate Adform ads into the Google Mobile Ads mediation platform.

# Integration

## Getting started

1. If you haven't integrated the Admob SDK, please do so, you could find documentation [here](https://firebase.google.com/docs/admob/android/quick-start).
2. You need to import Adform Advertising SDK to your project. Instructions on how to it you can find [here](https://github.com/adform/adform-android-sdk/wiki/Getting-Started).
3. Download our Admob adapter library and include into your project. You could download it from [here](https://github.com/adform/adform-advertising-admob-adapter-android/blob/master/AdformAdmobAdapter.jar?raw=true).
4. Then you have to configure banner or interstitial custom event in Admob interface. More information on how to do so you can find [here](https://firebase.google.com/docs/admob/android/custom-events). There are two very important steps when defining a custom event:

	* You must set master tag id provided by Adform in parameter field.
	* You must use `com.adform.admob.AdformCustomEventBanner` class for inline ads and `com.adform.admob.AdformCustomEventInterstitial` class for interstitial ads (class name field).

## Passing additional parameters to Adform banners

Additionally you can pass key values to mediated Adform banners.

When creating the AdRequest for an AdMob interstitial create an Android Bundle object with your keyvalues as extras (see example below). Add your custom Bundle to the AdRequest using `addCustomEventExtrasBundle(<adform adater class>, <var name for your bundle>)`

```java
 	Bundle bundle = new Bundle();
    bundle.putString("age", "41");
    AdRequest adRequest = new AdRequest.Builder()
            .addCustomEventExtrasBundle(AdformCustomEventBanner.class, bundle)
            .build();

