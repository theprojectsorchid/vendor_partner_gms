## microG Mobile Services

## OrchidOS ROM secure minimal and alternative Google services 
This is a collection of FOSS APKs, coupled with the respective Makefiles for an
easy integration in the Android build system.

To include them in your build, add a repo manifest file to include this repository as `vendor/partner_gms` and set
`WITH_GMS` to `true` when building.

Example manifest:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
    <project path="vendor/partner_gms" name="theprojectorchid/vendor_partner_gms" remote="github" revision="OrchidOstemplate" />
</manifest>
```

Alternatively:
```
You can include this repo:
git clone https://github.com/theprojectorchid/vendor_partner_gms -b OrchidOStemplate vendor/partner_gms 
Within your root directory 

You can include a vendor call at the Top of your common.mk file found within the vendor/(yourRom)/config folder:
$(call inherit-product-if-exists, vendor/partner_gms/gms.mk)

Also add this lower in same file:
#microg
WITH_GMS=true
```

The included APKs are:
   * Aurora Store, Droid, and Services (https://gitlab.com/AuroraOSS). Pre-signed prebuilts by dev (from gitlab always).
   * microG packages (binaries sourced from [here](https://microg.org/download.html))
   * GmsCore: the main component of microG, a FOSS reimplementation of the Google Play Services (requires GsfProxy and FakeStore for full functionality)
   * GsfProxy: a GmsCore proxy for legacy GCM compatibility
   * FakeStore: an empty package that mocks the existence of the Google Play Store
   * IchnaeaNlpBackend: Network location provider using Mozilla Location Service
   * NominatimGeocoderBackend: Geocoder backend that uses OSM Nominatim service
   * Googlecontact, Calendar and Backup options: for the choice to enable sync 

These are official unmodified prebuilt binaries, signed by the
corresponding developers.

Thank you to all developers for all the hard work 
