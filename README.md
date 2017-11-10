# JS Utility Library

Utility Library for Aurelia UI Framework

---

### Installing

```shell
yarn add auf-utility-library
```

### Utilities

* `Countries`: Complete list of world countries
* `Currencies`: Complete list of world currencies
* `PhoneLib`: Phone number validator and formatter

### Global Utilities
```ts
// get browser agent
browserAgent()

UA_EDGE = "ua-edge";
UA_OPERA = "ua-opera";
UA_CHROME = "ua-chrome";
UA_SAFARI = "ua-safari";
UA_FIREFOX = "ua-firefox";
UA_UNKNOWN = "ua-unknown";

// check methods
isTrue(true|1|yes|on)
isFalse(false|0|no|off)

isString()
isNumber()
isDecimal()

// Convert latin character string into ASCII equivalent
getAscii()
```

### Using Countries
A utility that provides country details
```ts
// Get full list
Countries.list

// Find country by code (iso 2 or iso 3 country code)
Countries.find(code)

// Get Iso country code
Countries.toIso2(code3)
Countries.toIso3(code2)

// Country Model
{
  "continent": "North America",
  "iso2": "US",
  "iso3": "USA",
  "name": "United States of America",
  "tld": ".us",
  "currency": "USD",
  "phone": "+1"
}
// TODO: Need to add currency prefix character when available
```

### Using Currencies
A simple POJO map of currency id and names
```ts
Currencies.USD = 'United States Dollar';
Currencies.INR = 'Indian Rupee';
```

### Using PhoneLib
PhoneLib is built using Google Phone Number library

```ts
// Check validity
PhoneLib.isValid(string, countryCode2);

// Format phone number
PhoneLib.format(string, countryCode2, format);

// Get phone number information
PhoneLib.getNumberInfo(string, countryCode2):{countryCode, areaCode, phone, ext}

// Get international dialing code
PhoneLib.getDialingCode(countryCode);

// Get format example for country
PhoneLib.getExample(countryCode, type, nationalFormat);
//PhoneLib.getExample('us', PhoneLib.TYPE.MOBILE, true);

// Get iso code from phone number, must be a full international dialing number
PhoneLib.getIso2Code(string);

// Types
PhoneLib.TYPE.MOBILE
PhoneLib.TYPE.FIXED_LINE
PhoneLib.TYPE.FIXED_LINE_OR_MOBILE

// Formats
PhoneLib.FORMAT.NATIONAL
PhoneLib.FORMAT.INTERNATIONAL
PhoneLib.FORMAT.FULL // Unformatted number with dialing code
PhoneLib.FORMAT.LINK // Full number with tel: prefix
```

> NOTE: `countryCode2` must be provided if the number provided is not prefixed with an international dialing code
