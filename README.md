FacebookLogin
=============


This is just to refer how to achieve facebook login using facebook 3.5 SDK. 

Following functionalities have been covered in this sample :

1) Login using facebook sdk 3.5

2) logout functionality

3) Display user info

4) share content to user wall using FBDialog

5) show facebook friends using FQL Queries and invite them.

6) Show facebook friends who are using same app and invite them.




Meanwhile you can download facebook SDK from Link below :

https://developers.facebook.com/ios/


If you are getting Errors like SDK error 2 then please configure your app properly. or follow following guideline that i found on stack overflow.

1. Make sure you've setup your App on Facebook correctly
You need to set how your App integrates with Facebook to Native iOS App and enter the Bundle ID of your App into the designated field. You can set the iTunes ID to 0 for now. Enable Facebook Login and set the App Type in the advanced settings tab to Native/Desktop.
Also set App Secret in Client to No.

If one or more of these options are not set correctly it's very likely you get the error The Facebook server could not fulfill this access request: remote_app_id does not match stored id.

2. Installing the Facebook App for the first time
When first installing an App via the native Facebook integration on iOS (and Mac OS X too), you must ask for a basic read permission only! Nothing else as email, user_birthday and user_location is allowed here. Using user_about_me, which is also a basic read permission according to the Facebook documentation, does not work. This is pretty confusing if you previously worked with the Facebook JavaScript SDK or the Facebook PHP SDK, because it asks for the basic permissions by default without you having to do something. Facebook also updated their documentation with a short step-by-step guide on how to use the new Facebook SDK on iOS 6.

3. Requesting additional permissions
It's important to know, that you may not ask for read and write permissions at the same time. That's also something experienced Facebook SDK developers may find confusing. Requesting the read_stream permission along with the publish_stream permission will make the request fail, resulting in the error An app may not aks for read and write permissions at the same time.

As Facebook does not really distinguish between read/write permissions in the Permission Reference, you must identify write permissions by yourself. They're usually prefixed with manage_*, publish_*, create_* or suffixed by *_management.

Facebook does also not recommend to ask for additional permissions immediately after getting basic permissions. The documentation says "You are now required to request read and publish permission separately (and in that order). Most likely, you will request the read permissions for personalization when the app starts and the user first logs in. Later, if appropriate, your app can request publish permissions when it intends to post data to Facebook. [...] Asking for the two types separately also greatly improves the chances that users will grant the publish permissions, since your app will only seek them at the time it needs them, most likely when the user has a stronger intent.".

Or you can refer more details here :

http://stackoverflow.com/questions/12644229/ios-6-facebook-posting-procedure-ends-up-with-remote-app-id-does-not-match-stor


