title= Overview
date=2013-08-25
type=overview
tags=blog
status=published
~~~~~~


# IPGeolocation

IPGeolocation provides three APIs:  
[IP Geolocation API](https://ipgeolocation.io/documentation/ip-geolocation-api-201812061140)  
IP Geolocation API can be used to get real-time and accurate geolocation for any IP address. You can geolocate your online visitors and provide them customized experience accordingly.  
* [Timezone API](https://ipgeolocation.io/documentation/timezone-api-201812061213)  
The Timezone API can be used to get accurate, real-time date, time and timezone information.  
* [Astronomy API](https://ipgeolocation.io/documentation/astronomy-api-201812061214)  
The Astronomy API can used to get the location-based rise and set times for the Sun and the Moon, including current position, angle, and distance of the Sun and the Moon for a date.

This documentation provides complete details of features and available options in the above APIs. For information related to our IP Geolocation API Database, please [contact](https://ipgeolocation.io/contact) our support.

## Authorization

We provide two ways of authorization which are, by using the:  
* API Key  
* Request Origin

In order to use the APIs, [sign up](https://ipgeolocation.io/signup) for a desired plan. 

All of our paid plans come with 7 days free trial. We also have a free plan which gives you 1500 requests per day. We provide the same API response in our free as well as paid plans over https. _Response in multiple languages_, _Bulk IP Geolocation Lookup_ and _Request Origin Support_ are not available for free plans, however.

Here is an overview of both authorization methods.

### API Key

You can make authorized requests to our API by passing API key as a query parameter. To get your API key, login to our API console and get your API key from there. We strongly discourage the use of API key in client-side JavaScript as it will expose your API key to the public. 

In order to use API key in the client-side JavaScript, use the _Request Origin_ approach.

### Request Origin

This feature is available for paid plans only. The purpose of this feature is to call our API from the client-side JavaScript without using your API key. 

To use this feature, go to application console and click on `Add New` button in the dashboard section. A popup will open up. Enter the domain name of the website from where you'll be making requests. If your website is https://www.example.com, you should enter `example.com` in that pop up as your request origin. 

Once saved successfully, you can make requests from the main domain as well as all of the subdomains of the main website.

#### Limit on No. of Request Origins

The number of request origins is limited based on the user's plan.

|Subscription Plan|No. of Request Origins|
|-----------------|----------------------|
|Bronze|1|
|Bronze+|1|
|Silver|2|
|Silver+|2|
|Gold|3|
|Platinum|3|
|Diamond|3|

To add more request origin than your limit, you can leave a message at [contact us](https://ipgeolocation.io/contact). Extra request origins are charged $2.5 per month each.

## Get IP

Get IP endpoint returns the IP address of the client from where it's called. So if you call it from your server, it returns IP address of the server. If it's called from your website like using JavaScript, it will return the IP address of the person viewing your website. This endpoint does not require any authentication and you can use this endpoint without creating an account. Here is a ```curl``` example:

```curl
$ curl 'https://api.ipgeolocation.io/getip'

{
    "ip": "1.1.1.1"
}
```

## JSON and XML Response Formats

All the endpoints of IPGeolocation API can respond in JSON and XML formats, JSON is the default response format.

### XML Format

You can get API response in XML format in two ways:
1. Pass **output=xml** as a URL parameter.
2. Set **Accept** HTTP Header to **application/xml** or **text/xml**.

Here are a few examples of XML response:

```curl
$ curl 'https://api.ipgeolocation.io/ipgeo?apiKey=API_KEY&ip=1.1.1.1&fields=city&output=xml'

<?xml version="1.0" encoding="UTF-8"?>
<result>
    <ip>1.1.1.1</ip>
    <city>South Brisbane</city>
</result>

$ curl 'https://api.ipgeolocation.io/ipgeo?apiKey=API_KEY&ip=1.1.1.1&fields=currency' -H 'Accept: text/xml'

<?xml version="1.0" encoding="UTF-8"?>
<result>
    <ip>1.1.1.1</ip>
    <currency>
        <code>AUD</code>
        <name>Australian Dollar</name>
        <symbol>A$</symbol>
    </currency>
</result>
```

If you don't set **output** URL parameter or **Accept** header, the API will respond in JSON format.

## Security / SSL

We take security seriously and all of our API endpoints are served over a secure HTTPS connection for all users, even if you are on the free plan. 

## Rate Limits

We don't have any daily, hourly or monthly rate limit on any of our paid plans. If you increase from your monthly quota, we'll keep serving your requests and add a surcharge amount on top of your monthly price. Surcharge rate varies from plan to plan.

We have a hard limit of 1500 requests per day on our Free plan and 100,000 requests for 7 days on trial accounts.

## API SDKs

To facilitate the developers, we have added some SDKs for various programming languages. The detailed documentation on how to use these SDKs is available in the respective SDK's documentation page linked below. 

Our SDKs are also available on Github. Feel free to help us improve them. SDKs. Following are the available SDKs:

* [IP Geolocation API Java SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-java-sdk-20180807094025)
* [IP Geolocation API .NET SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-c-sharp-dot-net-sdk-201809031216)
* [IP Geolocation API Typescript SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-typescript-sdk-201809051239)
* [IP Geolocation API Javascript SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-javascript-sdk-201809051421)
* [IP Geolocation API PHP SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-php-sdk-201809051255)
* [IP Geolocation API JQuery SDK](https://ipgeolocation.io/documentation/ip-geolocation-api-jquery-sdk-201809051507)
