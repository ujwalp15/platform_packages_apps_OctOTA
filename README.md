OctOTA
-------
A very simple OTA checker with Android Settings look and feel.

How it works
------------
It parses the OTA xml file that you put in your file hosting and compares the version number with the local one.
If the version is newer, it notifies the user for a new ROM update.

How to use
----------
* Prepare the OTA xml file. Use this [template](https://raw.githubusercontent.com/Team-OctOS/OTA/oct-14.1/sample.xml).
* Upload it to your file hosting and create a hot link of it
* Copy the [ota_conf template](https://raw.githubusercontent.com/Team-OctOS/OTA/oct-14.1/ota_conf) to the root of rr source, as a text file called "ota_conf" (without the quotes)
* Template is also in https://raw.githubusercontent.com/Team-OctOS/packages_apps_OctOTA/oct-14.1/sample-ota_conf
* Replace the "ota_url" with your OTA xml hot link
* Check the xml template, and make your own, on your github, and place the resultant link to the raw file in the ota_conf
* If using the given samples, ota_conf is all setup! Else you will have to setup the version checking, etc.


### Most guys can skip the below part

Define how OctOTA should know about the "version". The version must be parseable to a date.
Usually, the version is a part of a build name. For example, the 20150426 in the SlimSaber-bacon-5.0.2-20150426.
Adjust the OTA configuration according to your build name on how should OctOTA parse the version
Find a key in build.prop that represents the  OCT-N-WEEKLY-20170107-0318-oneplus3.zip and set it in the "version_name"
Set the delimiter in "version_delimiter" to "-"
Set the date format in "version_format" to "yyyyMMdd"
Set the position in "version_position" to "3" (zero based)
Find a key in build.prop that represents your device name and set it in the "device_name"
OctOTA will search this device name in the OTA xml file


Credits
-------
* [SlimRoms team](http://Slimroms.net/)
  * For the original idea of the SlimCenter and app icon
* [CommonsWare Android Components](https://github.com/commonsguy/cwac-wakeful)
  * For the wakeful intent service that is used in this app
