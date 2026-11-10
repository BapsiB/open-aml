# Open AML: emergency location for Android without Google

**Status:** proposal. We are applying to the [Prototype Fund](https://prototypefund.de) (German Federal Ministry of Research funding for open source) to build this from June 2027. Nothing is built yet. We are looking for feedback and partners.

## The problem

When someone calls 112 from a normal Android phone or an iPhone, the phone quietly sends its position to the emergency centre. This is called Advanced Mobile Location (AML). Rescuers then know where the caller is, often to within a few metres.

On Android, AML is part of Google Play Services. It is closed source and is not in the Android Open Source Project. Phones running Android without Google, such as LineageOS, /e/OS, iodéOS or CalyxOS, therefore send no location when their user calls 112. A person in an emergency on one of these phones is harder to find than anyone with a stock phone.

Users have asked for this on the [/e/OS](https://community.e.foundation/t/e-os-and-google-android-emergency-location-service-els/73024) and [iodé](https://community.iode.tech/t/safety-mobile-net-functions/7921) forums. The [GrapheneOS forum](https://discuss.grapheneos.org/d/22208-location-services-for-emergency-calls) confirms the feature is not in AOSP. Sailfish OS has AML, but as a closed component. No open-source implementation exists.

## What we want to build

An open-source AML component that any Android system without Google can include:

- **Sends the standard message.** During an emergency call, it gets a position from satellites, Wi-Fi or mobile cells and sends it in the format of the [EENA/ETSI AML specification](https://eena.org/document/aml-specifications-requirements).
- **Only during an emergency call.** It turns location on for the call and for nothing else. At all other times the phone's privacy settings stay exactly as the user set them.
- **Per-country settings.** A configuration table for each country's emergency numbers and AML endpoint.
- **A test harness.** A simulator of the receiving side, so the component can be tested without sending anything to a real emergency centre.
- **Patches upstream.** Offered to LineageOS and microG, so systems built on them get AML without extra work.

## Safety first

A bug here could matter in a real emergency. The component will never be tested against live 112 endpoints without the agreement of the emergency service concerned. Development uses the simulator, then a test setup provided by an emergency centre or EENA.

## Who we are looking for

- **Android systems** (/e/OS, iodéOS, LineageOS, CalyxOS and others) willing to test the component and consider shipping it.
- **microG** as a possible home for the code.
- **Emergency centres and EENA** to check the messages against real practice and help with safe testing.

A short, non-binding letter of interest helps the funding application. We can send a draft.

## Plan

Six months of funded work from June 2027: design and simulator first, then the component and country settings, then testing with partners and patches upstream. All code will be published under an open-source licence (Apache-2.0, the same as AOSP and microG).

## Contact

Baptiste Bohelay, Android developer based in Berlin. [contact email]

English, Deutsch, français.
