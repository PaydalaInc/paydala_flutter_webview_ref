# Paydala WebView integration in Flutter

This is a reference application that demonstrates the use of Paydala payment widget inside the WebView of iOS and Android.

##Supported iOS and Android versions
This has been tested on iOS 16.x, 15.2 and Android API 32, 33

##Steps to integrate and build
### WebView integration
Follow code in main.dart to  to embed the widget `WebViewExample` in the operator's application. `WebViewExample` is a sample Flutter `StatefulWidget` that wraps Paydala Web widget in a WebView. Important thing is to define it as a StatefulWidget with the associated state defined in `_WebViewExampleState`. The reference application uses it to load the landing page as a place holder and the Paydala widget / paymnent flow  is invoked through the `_toLocationExample` event handler tied to the menu option "Pay with Paydala". This is just a demo use-case to show the start of payment flow. The WebViewExample widget can be customized to suit operator's requirement.  

### Use of CJWT
Replace `cjwt` value with the one obtained from the operator's CJWT endpoint. CJWT is the client (operator) Identity and Access Management (IAM) token used to identify the operator and the category for which payment is sought. It is a JSON Web Token (JWT) signed by the operator's private key and passed as the `authorization` header in the `loadUrl` call that launches Paydala widget URL.

###Build process
Follow these steps to run the application

```
git clone https://github.com/PaydalaInc/paydala_flutter_webview_ref.git

cd paydala_flutter_webview_ref

flutter clean

flutter pub get

flutter run

```

For additional help follow these instructions:
[https://docs.flutter.dev/get-started/test-drive]()

##Dependencies
This reference app depends on the following packages

* [location](https://pub.dev/packages/location)
* [flutter_webview_pro](https://pub.dev/packages/flutter_webview_pro)
