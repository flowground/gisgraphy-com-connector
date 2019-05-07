# ![LOGO](logo.png) Gisgraphy webservices **flow**ground Connector

## Description

A generated **flow**ground connector for the Gisgraphy webservices API (version 4.0.0).

Generated from: https://api.apis.guru/v2/specs/gisgraphy.com/4.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:40:55+03:00

## API Description

Since 2006, [Gisgraphy](http://www.gisgraphy.com) is a free, open source framework that offers the possibility to do geolocalisation and geocoding via Java APIs or REST webservices. Because geocoding is nothing without data, it provides an easy to use importer that will automatically download and import the necessary (free) data to your local database ([OpenStreetMap](http://www.openstreetmap.org/), [Geonames](http://www.geonames.org/) and [Quattroshapes](http://www.quattroshapes.com/): more than 100 million entries). You can also add your own data with the Web interface or the importer connectors provided. Gisgraphy is production ready, and has been designed to be scalable(load balanced), performant and used in other languages than just java : results can be output in XML, JSON, PHP, Python, Ruby, YAML, GeoRSS, and Atom. One of the most popular GPS tracking System (OpenGTS) also includes a Gisgraphy client...Gisgraphy is a framework. As a result it's flexible and powerful enough to be used in a lot of different use cases. [read more](http://www.gisgraphy.com)


if you use the premium servers, you can use the api key to test the webservices


## Authorization

Supported authorization schemes:
- API Key
## Actions

### split a raw address into several parts

> The address parser and address standardizer, are part of the Gisgraphy project (free open source worldwide geocoder). Address parsing is the process of dividing a single address string into its individual component parts. Please visit [http://www.address-parser.net](http://www.address-parser.net) for more details

*Tags:* `addressparser - standardizer`

#### Input Parameters
* `address` - _required_ - A postal address.
* `country` - _optional_ - The ISO 3166 Alpha 2 code of the country.
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML.
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results.Default to false. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'
* `standardize` - _optional_ - Whether the address should be standardized after parsing, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'
* `geocode` - _optional_ - UNUSED YET. Whether the address should be geocoded after parsing, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

### search for places by text around a GPS point

> The full text service allows you to search for features / places / street and do autocompletion . you can : Specify one or more words search on part of the name (auto completion / suggestion) Search for text or zip code Specify a GPS restriction (promote nearest, not sorted but has an impact on the score), Limit the results to a specific Language, Country, place type, Paginate the results, Specify the output verbosity, Tells if you want the output to be indented, Tells that all words are required or not, The search is case insensitive, use synonyms (Saint/st, ..), separator characters stripping, ...

*Tags:* `fulltext - autocomplete`

#### Input Parameters
* `q` - _required_ - The searched text : The text for the query can be a zip code, a string or one or more strings
* `allwordsrequired` - _required_ - Whether the fulltext engine should considers all the words specified as required. Defaults to false (since v 4.0). possible values are true|false (or 'on' when used with the rest service)
* `spellchecking` - _optional_ - The spellchecking (optional) : whether some suggestions should be provided if no results are found
* `lat` - _optional_ - The latitude (north-south) for the location point to search around. The value is a floating number, between -90 and +90. It uses GPS coordinates
* `lng` - _optional_ - TThe longitude (east-West) for the location point to search around. The value is a floating number between -180 and +180. It uses GPS coordinates.
* `radius` - _optional_ - distance from the location point in meters we'd like to search around. The value is a number > 0 if it is not specify or incorrect.
* `suggest` - _optional_ - If this parameter is set then it will search in part of the names of the street, place,.... It allow you to do auto completion auto suggestion. See the Gisgraphy leaflet plugin for more details. The JSON format will be forced if this parameter is true. See auto completion / suggestions engine for more details
* `style` - _optional_ - The output style verbosity (optional) : Determines the output verbosity. 4 styles are available
    Possible values: SHORT, MEDIUM, LONG, FULL.
* `country` - _optional_ - limit the search to the specified ISO 3166 country code. Default : search in all countries
* `lang` - _optional_ - The language code (optional) : The iso 639 Alpha2 or alpha3 Language Code. Some properties such as the AlternateName AdmNames and countryname belong to a certain language code. The language parameter can limit the output of those fields to a certain language (it only apply when style parameter='style') : If the language code does not exists or is not specified, properties with all the languages are retrieved If it exists, the properties with the specified language code, are retrieved
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML, ATOM, GEORSS.
* `from` - _optional_ - The first pagination index. Numbered from 1. If the number is < 1 or not specified, it will be set to the default value : 1
* `to` - _optional_ - The last pagination index. if < 1 or not specified, it will be set to startindex + 10. Max = 10 (can be changed)
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results.Default to false. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

### Geocode an address

> The Gisgraphy geocoding service allows you to transform postal addresses or other descriptions (a street, a city, a postal code, a country, or a combination) of a location into a (latitude, longitude) coordinate.

*Tags:* `geocoding`

#### Input Parameters
* `address` - _required_ - A postal address, structured or not, a street, a city, a postal code, a country, or a combination.
* `country` - _optional_ - The country where the place/address is. It is used to determine the postal address format and to improve performance. It will probably be optional in next version to ease the usability. The value must be the ISO 3166 Alpha 2 code of the country.
* `postal` - _optional_ - Whether the given address is a postal address. default to false. In other words, if the address follow the specification or if it is a well-formed address as it was written on an envelope. This parameter will enable the parsing of the address by the address parser before geocoding, this way, the relevance will be better because because if parsing is successful, we will know the meaning of each word. Note that you can also specify each field if you already know them.
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML.
* `from` - _optional_ - The first pagination index. Numbered from 1. If the number is < 1 or not specified, it will be set to the default value : 1
* `to` - _optional_ - The last pagination index. if < 1 or not specified, it will be set to startindex + 10. Max = 10 (can be changed)
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

### Geocode an address

> The geolocalisation service allows to search for features around a earth location. you can Specify GPS position, Limit the results to a specific place type (e.g : search all monuments around a point), Limit the results to a specified radius, Paginate the results, Tells if you want the output to be indented (currently, applies only for XML, not JSON for performance reasons. May change in next version)

*Tags:* `geolocalisation`

#### Input Parameters
* `lat` - _required_ - The latitude (north-south) for the location point to search around. The value is a floating number, between -90 and +90. It uses GPS coordinates
* `lng` - _required_ - TThe longitude (east-West) for the location point to search around. The value is a floating number between -180 and +180. It uses GPS coordinates.
* `radius` - _optional_ - distance from the location point in meters we'd like to search around. The value is a number > 0 if it is not specify or incorrect.
* `distance` - _optional_ - Whether (or not) we want the distance field to be output. This option is useful to improve the performance if we don't care about the distance (e.g : we search for name). Of course, the results won't be sorted by distance. If you use a checkbox in a form to indent the results, the value will be 'on' or 'off', so to simplify the use : the value for the web service can be 'true' or 'on'
* `placetype` - _optional_ - filter search for a given placetype
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML.
* `from` - _optional_ - The first pagination index. Numbered from 1. If the number is < 1 or not specified, it will be set to the default value : 1
* `to` - _optional_ - The last pagination index. if < 1 or not specified, it will be set to startindex + 10. Max = 10 (can be changed)
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results.Default to false. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

### Reverse geocode an address

> The Reverse geocoding service allows to search for an address for a given GPS position.

*Tags:* `reversegeocoding`

#### Input Parameters
* `lat` - _required_ - The latitude (north-south) for the location point to search around. The value is a floating number, between -90 and +90. It uses GPS coordinates
* `lng` - _required_ - TThe longitude (east-West) for the location point to search around. The value is a floating number between -180 and +180. It uses GPS coordinates.
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML.
* `from` - _optional_ - The first pagination index. Numbered from 1. If the number is < 1 or not specified, it will be set to the default value : 1
* `to` - _optional_ - The last pagination index. if < 1 or not specified, it will be set to startindex + 10. Max = 10 (can be changed)
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

### Geocode an address

> The street service allows you to search for street by GPS position. You can : Specify GPS position, Give the beginning or a part of the name of the street (useful for autocompletion), Limit search to a specific type (e.g : Pedestrian, highway, residential, ... 25 types available), Limit search to a specified radius, Limit search to one way streets,

*Tags:* `streetservice`

#### Input Parameters
* `lat` - _required_ - The latitude (north-south) for the location point to search around. The value is a floating number, between -90 and +90. It uses GPS coordinates
* `lng` - _required_ - TThe longitude (east-West) for the location point to search around. The value is a floating number between -180 and +180. It uses GPS coordinates.
* `radius` - _optional_ - distance from the location point in meters we'd like to search around. The value is a number > 0 if it is not specify or incorrect.
* `oneway` - _optional_ - whether the street should be a oneWay street (optional) : limit the search to the street that are one way street. If you use a checkbox in a form to indent the results, the value will be 'on' or 'off', so to simplify the use : the value for the web service can be 'true' or 'on'
* `distance` - _optional_ - Whether (or not) we want the distance field to be output. This option is useful to improve the performance if we don't care about the distance (e.g : we search for name). Of course, the results won't be sorted by distance. If you use a checkbox in a form to indent the results, the value will be 'on' or 'off', so to simplify the use : the value for the web service can be 'true' or 'on'
* `streettype` - _optional_ - filter search with a stret type
* `format` - _optional_ - The output format.
    Possible values: XML, JSON, PHP, RUBY, PYTHON, YAML.
* `from` - _optional_ - The first pagination index. Numbered from 1. If the number is < 1 or not specified, it will be set to the default value : 1
* `to` - _optional_ - The last pagination index. if < 1 or not specified, it will be set to startindex + 10. Max = 10 (can be changed)
* `callback` - _optional_ - The callback method name (optional), use to wrap the content into a (alphanumeric) Javascript method. Works only for script output formats (JSON, PHP, Ruby, Python)
* `indent` - _optional_ - indents the results. Possible values are true or false (or on when used with the rest service. If you use a checkbox in a web form, to indent the results, the value will be 'on' or 'off', so for a simple use : the value of indent can be 'true' or 'on'

## License

**flow**ground :- Telekom iPaaS / gisgraphy-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
