![IAB Tech Lab](https://drive.google.com/uc?id=10yoBoG5uRETSXRrnJPUDuONujvADrSG1)

# **AdCOM Specification v1.0**

#### Final v 1.0

**November 2018**


**About the IAB Technology Lab**


The IAB Technology Laboratory (Tech Lab) is a non-profit research and development consortium that produces and provides standards, software, and services to drive growth of an effective and sustainable global digital media ecosystem. Comprised of digital publishers and ad technology firms as well as marketers, agencies, and other companies with interests in the interactive marketing arena, IAB Tech Lab aims to enable brand and media growth via a transparent, safe, effective supply chain, simpler and more consistent measurement, and better advertising experiences for consumers, with a focus on mobile and TV/digital video channel enablement. The IAB Tech Lab portfolio includes the DigiTrust real-time standardized identity service designed to improve the digital experience for consumers, publishers, advertisers, and third-party platforms.  Board members include AppNexus, ExtremeReach, Google, GroupM, Hearst Digital Media, Integral Ad Science, Index Exchange, LinkedIn, MediaMath, Microsoft, Moat, Pandora, PubMatic, Quantcast, Telaria, The Trade Desk, and Yahoo! Japan. Established in 2014, the IAB Tech Lab is headquartered in New York City with an office in San Francisco and representation in Seattle and London.

Learn more about IAB Tech Lab here: [www.iabtechlab.com](https://www.iabtechlab.com) 

**License**

OpenRTB Specification the IAB Tech Lab is licensed under a Creative Commons Attribution 3.0 License. To view a copy of this license, visit [creativecommons.org/licenses/by/3.0/](http://creativecommons.org/licenses/by/3.0/) or write to Creative Commons, 171 Second Street, Suite 300, San Francisco, CA 94105, USA.

![](https://drive.google.com/uc?id=1GsSz9KPUksmllzcn4v4v0rFxizNNXt-S)



# Table of Contents
- [OVERVIEW](#Overview)
  - [OpenMedia Mission](#openmediamission)
  - [AdCOM Executive Summary](#execsummary)
  - [Version History](#versionhistory)
- [ARCHITECTURE](#architecture)
  - [OpenMedia Layers](#openmedialayers)
  - [AdCOM Principles](#adcomprinciples)
- [SPECIFICATION](#spec)
  - [Media Objects](#mediaobjects)
    - [Object:  Ad](#object_ad)
    - [Object:  Display](#object_display)
    - [Object:  Banner](#object_banner)
    - [Object:  Native](#object_native)
    - [Object:  Asset](#object_asset)
    - [Object:  LinkAsset](#object_linkasset)
    - [Object:  TitleAsset](#object_titleasset)
    - [Object:  ImageAsset](#object_imageasset)
    - [Object:  VideoAsset](#object_videoasset)
    - [Object:  DataAsset](#object_dataasset)
    - [Object:  Event](#object_event)
    - [Object:  Video](#object_video)
    - [Object:  Audio](#object_audio)
    - [Object:  Audit](#object_audit)
  - [Placement Objects](#placementobjects)
    - [Object:  Placement](#object_placement)
    - [Object:  DisplayPlacement](#object_displayplacement)
    - [Object:  DisplayFormat](#object_displayformat)
    - [Object:  NativeFormat](#object_nativeformat)
    - [Object:  AssetFormat](#object_assetformat)
    - [Object:  TitleAssetFormat](#object_titleassetformat)
    - [Object:  ImageAssetFormat](#object_imageassetformat)
    - [Object:  DataAssetFormat](#object_dataassetformat)
    - [Object:  EventSpec](#object_eventspec)
    - [Object:  VideoPlacement](#object_videoplacement)
    - [Object:  AudioPlacement](#object_audioplacement)
    - [Object:  Companion](#object_companion)
  - [Context Objects](#contextobjects)
    - [Abstract Class:  DistributionChannel](#abstract_distributionchannel)
    - [Object:  Site](#object_site)
    - [Object:  App](#object_app)
    - [Object:  Dooh](#object_dooh)
    - [Object:  Publisher](#object_publisher)
    - [Object:  Content](#object_content)
    - [Object:  Producer](#object_producer)
    - [Object:  User](#object_user)
    - [Object:  Device](#object_device)
    - [Object:  Geo](#object_geo)
    - [Object:  Data](#object_data)
    - [Object:  Segment](#object_segment)
    - [Object:  Regs](#object_regs)
    - [Object:  Restrictions](#object_restrictions)
  - [Enumerations](#enumerations)
    - [List:  API Frameworks](#list_apiframeworks)
    - [List:  Audit Status Codes](#list_auditstatuscodes)
    - [List:  Category Taxonomies](#list_categorytaxonomies)
    - [List:  Click Types](#list_clicktypes)
    - [List:  Companion Types](#list_companiontypes)
    - [List:  Connection Types](#list_connectiontypes)
    - [List:  Content Contexts](#list_contentcontexts)
    - [List:  Creative Attributes](#list_creativeattributes)
    - [List:  Creative Subtypes - Audio/Video](#list_creativesubtypesaudiovideo)
    - [List:  Creative Subtypes - Display](#list_creativesubtypesdisplay)
    - [List:  Delivery Methods](#list_deliverymethods)
    - [List:  Device Types](#list_devicetypes)
    - [List:  Display Context Types](#list_displaycontexttypes)
    - [List:  Display Placement Types](#list_displayplacementtypes)
    - [List:  DOOH Venue Types](#list_doohvenuetypes)
    - [List:  Event Tracking Methods](#list_eventtrackingmethods)
    - [List:  Event Types](#list_eventtypes)
    - [List:  Expandable Directions](#list_expandabledirections)
    - [List:  Feed Types](#list_feedtypes)
    - [List:  IP Location Services](#list_iplocationservices)
    - [List:  Linearity Modes](#list_linearitymodes)
    - [List:  Location Types](#list_locationtypes)
    - [List:  Media Ratings](#list_mediaratings)
    - [List:  Native Data Asset Types](#list_nativedataassettypes)
    - [List:  Native Image Asset Types](#list_nativeimageassettypes)
    - [List:  Operating Systems](#list_operatingsystems)
    - [List:  Placement Positions](#list_placementpositions)
    - [List:  Placement Subtypes - Video](#list_placementsubtypesvideo)
    - [List:  Playback Cessation Modes](#list_playbackcessationmodes)
    - [List:  Playback Methods](#list_playbackmethods)
    - [List:  Production Qualities](#list_productionqualities)
    - [List:  Size Units](#list_sizeunits)
    - [List:  Start Delay Modes](#list_startdelaymodes)
    - [List:  Volume Normalization Modes](#list_volumenormalizationmodes)
- [Appendix A:  Additional Resources](#appendixa_additionalresources)
- [Appendix B:  Change Log](#appendixb_changelog)
- [Appendix C:  OpenRTB Interfaces](#appendixc_openrtbinterfaces)
  - [Request Context](#requestcontext)
  - [Item Specifications](#itemspecs)
  - [Media Response](#mediaresponse)



# OVERVIEW <a name="Overview"></a>

## OpenMedia Mission <a name="openmediamission"></a>

The mission of the OpenMedia project is to spur growth in programmatic marketplaces by providing open industry standards for communication between buyers of advertising and sellers of publisher inventory.  There are several aspects to these standards including but not limited to real-time bidding, ad and creative management, information taxonomies, and many more.

Over recent years, multiple IAB standards have reached considerable levels of success in the industry.  OpenMedia is the umbrella that pulls these standards into a coherent landscape and in doing so, it has become clear that there are many core concepts that are overlapping from these multiple specifications.  This document presents a standard that formalizes these common concepts for reuse by other standards so that they can focus on their distinctiveness and practitioners can find it easier to build systems that use multiple aspects of OpenMedia.

## AdCOM Executive Summary <a name="execsummary"></a>

One of the most successful IAB standards is OpenRTB.  This protocol for conducting real-time auctions among sell-side exchanges and demand-side bidders first launched as OpenRTB v1.0 Mobile in February 2011.  Later that year, OpenRTB v2.0 was released, which provided a unified protocol for mobile, display, and video.  Due to widespread industry adoption, OpenRTB was established as an IAB standard in January 2012 with the release of version v2.1 although governance over technical content remained with the OpenRTB community.  Since then and true to its initial objective, OpenRTB has become the *lingua franca* of real-time programmatic advertising and entered 2018 as v2.5.

During these years, programmatic advertising has become a dominant force in the industry.  However, this has also led to an increasingly complex supply chain which may increase fraud rates and other risks.  This is one of the key motivators driving OpenRTB v3.0 since the level of change needed to meet the challenges of programmatic currently and going forward could not be accomplished in a backward compatible manner (i.e., as an additional v2.x release).

Combined with the OpenMedia goal of rationalizing the IAB standards portfolio, this has led to a layered approach, where OpenRTB will focus on the actual media commerce transaction (e.g., auction parameters, deals, bids, etc.) while the concepts in common with other specifications (e.g., ads, placements, users, devices, sites, publishers, etc.) will be factored into its own reusable specification.  Thus the genesis of the Advertising Common Object Model or AdCOM.

In addition to providing the modularity to benefit specifications in addition to OpenRTB, AdCOM seeks to address other business challenges of programmatic advertising.  For example, publishers currently have limited ability to control the types of creatives they run on their properties due to the opaque nature in which traditional display ads are conveyed.  Many types of undesirable creatives make their way to publisher content such as overly heavy payloads, those lacking of brand safety, excessive pixel fires, and JavaScript that launches malware.

These and other problematic behaviors result in poor and potentially damaging user experiences, diminished user trust, installation of ad blockers, erosion of publisher monetization, and the increased challenge for good actors on the advertiser side to reach their intended audience.  AdCOM attempts to address these challenges by supporting new and safer structured ad formats.

Reusability by multiple IAB specifications positions AdCOM to leverage solutions such as this across a range of industry applications.

## Version History <a name="versionhistory"></a>

1.0	Original Release of AdCOM; the Advertising Common Object Model.

# ARCHITECTURE <a name="architecture"></a>

This section describes the OpenMedia specification landscape, the role AdCOM plays, its overall structure, and the principles that guide the usage and extensibility of the AdCOM specification.

## OpenMedia Layers <a name="openmedialayers"></a>

To assist in reuse of objects across different specifications and to enable specifications to evolve at different paces, a layered approach is being adopted.  Expressed informally, Layer-1 moves bytes among parties, Layer-2 expresses the language of these bytes, Layer-3 specifies a transaction using this language, and Layer-4 describes the concepts being transacted.

![](https://drive.google.com/uc?id=1RN-UxDGvP4F1ECiVvHl7BJODBh2oi0uZ)

Given this layered concept, the IAB Tech Lab has defined an overall organization of related specifications as "OpenMedia".  The landscape of these specifications and how they may be organized into protocol layers is illustrated as follows.

![](https://drive.google.com/uc?id=1oJ7_sDwDzVKbu3vXXIifjc-Ki7LiOkvI)

There are a number of objects that are common to multiple transaction specifications. For example, both OpenRTB and OpenDirect share a common concept of a "site", a "placement", an "ad", and other so-called domain objects. These objects describe the subject of a transaction; those concepts upon which the transaction operates. Factoring them into their own model enables multiple transaction protocol specifications to reuse these common objects rather than each of them redefining similar but needlessly different versions of core concepts.

## AdCOM Principles <a name="adcomprinciples"></a>

The following points define the guiding principles underlying the AdCOM specification, some of its basic rules, and its evolution.

* AdCOM is backwards compatible within minor versions (e.g. 1.x to 1.y).  No breaking changes may be made within a minor revision (e.g., no removal of attributes or objects, name or type changes, or redefinition of semantics).  New objects and attributes may be added and enumerated lists may be extended and thus implementers must accept these types of changes without breakage.

* Object and attribute names have been made intentionally compact while still trying to balance readability.  The reason for this is that in applications like OpenRTB where JSON is still widely used, these names may be transmitted in plain text extremely frequently.

* When using AdCOM, transaction specifications (e.g. OpenRTB) must indicate the version of AdCOM in use and specify where and how it interfaces with AdCOM objects.

* AdCOM imposes no specific representation on its objects.  This document uses JSON for illustration purposes, but this is not intended to imply any representational requirement or language binding.

* All AdCOM objects may be extended as needed for vendor-specific applications.  Extensions to an AdCOM object must always be placed within a subordinate "ext" object.  Most enumerated lists when indicated can also be extended to include vendor-specific codes typically starting at 500.

* The typical process of promoting a new AdCOM object, attribute, or list value into future specification versions is either when a substantial concept is discovered that is applicable to multiple transaction specifications or when vendor-specific extensions become widely adopted.

# SPECIFICATION <a name="spec"></a>

This section contains the detailed AdCOM domain layer specification.  Unless explicitly specified otherwise, annotated as optional, or called out as a best practice, all material aspects of this section are required for AdCOM compliance.

Throughout the object specifications, attributes may be indicated as "Required" or "Recommended". Attributes are deemed *required* only if their omission would break the technical meaning of the object and is not necessarily an indicator of business value otherwise. Attributes are *recommended* when their omission would not break the object, but would dramatically diminish its value. Transaction layers in which AdCOM is used may provide additional *required* and/or *recommended* guidance specific to the application.

From a specification compliance perspective, any attribute not denoted *required* is optional, whether *recommended* or not. An optional attribute may have a default value to be assumed if omitted. If no default is indicated, then by convention its absence should be interpreted as *unknown*, unless otherwise specified. Empty strings or null values should be interpreted the same as omitted (i.e., the default if one is specified or *unknown* otherwise).

AdCOM is a collection of object classes with various relationships among them. However, there are distinct groups into which these classes are partitioned. The figure below identifies these groups as *Media*, *Placement*, and *Context*. This is purely a means of organization; no technical distinctions or restrictions are implied.

![](https://drive.google.com/uc?id=1K5erLjElcSJFLPYbcByQsljS2il-O_bC)

The Media group comprises objects that define an actual ad, including reference to its creative and metadata to enable proper rendering, restrictions compliance, event tracking, and quality auditing.

The Placement group comprises objects that define the set of allowed ads and behaviors for a given placement.  This might include mechanical information (e.g., sizes, supported mime types, and other rendering options), placement details and positioning, and various restrictions lists.

Finally, the Context group comprises objects that represent concepts that are interacting, presenting, enclosing, or are otherwise relating to the world in which impressions live.  These include the user, their device, their location, the ad distribution channel (e.g., site, app, digital out-of-home) with which they are interacting, the channel's publisher, its content, and any regulations that are in effect.

Note: As a convention in this document, objects being defined are denoted with uppercase first letter in deference to the common convention for class names in programming languages such as Java, whereas actual instances of objects and references thereto are lowercase.

## Media Objects <a name="mediaobjects"></a>

The Media group of objects defines an actual ad including reference to its creative and metadata to enable proper rendering, restrictions compliance, event tracking, and quality auditing.

The following figure presents the objects and interrelationships in this group. The objects are defined in the subsections thereafter.

![](https://drive.google.com/open?id=1mp4eInBTtsn0eihc09D-7GoIJ-5XIDv6)

### Object:  Ad <a name="object_ad"></a>

This object is the root of a structure that defines in instance of advertising media.  It includes metadata about the ad overall and sub-objects that provide additional detail specific to the type of media comprising the creative.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string; required</td>
    <td>ID of the creative; unique at least throughout the scope of a vendor (e.g., an exchange or buying platform).  Note that multiple instances of the same ad when used in transactions must have the same ID.</td>
  </tr>
  <tr>
    <td>adomain</td>
    <td>string array; recommended</td>
    <td>Advertiser domain; top two levels only (e.g., "ford.com").  This can be an array for the case of rotating creatives.</td>
  </tr>
  <tr>
    <td>bundle</td>
    <td>string array</td>
    <td>When the product of the ad is an app, the unique ID of that app as a bundle or package name (e.g., "com.foo.mygame").  This  should NOT be an app store ID (e.g., no iTunes store IDs).  This can be an array of for the case of rotating creatives.</td>
  </tr>
  <tr>
    <td>iurl</td>
    <td>string</td>
    <td>URL without cache-busting to an image that is representative of the ad content for cursory level ad quality checking.</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories describing the ad using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer; default 2</td>
    <td>The taxonomy in use for the "cat" attribute.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>lang</td>
    <td>string</td>
    <td>Language of the creative using ISO-639-1-alpha-2.  In practice, vendors using this object may elect an alternate standard (e.g., BCP-47) in which case this must be communicated a priori.  The non-standard code "xx" may also be used if the creative has no linguistic content (e.g., a banner with just a company logo).</td>
  </tr>
  <tr>
    <td>attr</td>
    <td>integer array</td>
    <td>Set of attributes describing the creative.  Refer to List:  Creative Attributes.</td>
  </tr>
  <tr>
    <td>secure</td>
    <td>integer</td>
    <td>Flag to indicate if the creative is secure (i.e., uses HTTPS for all assets and markup), where 0 = no, 1 = yes.  There is no default and thus if omitted, the secure state is unknown.  However, as a practical matter, the safe assumption is to treat unknown as non-secure.</td>
  </tr>
  <tr>
    <td>mrating</td>
    <td>integer</td>
    <td>Media rating per IQG guidelines.  Refer to List:  Media Ratings.</td>
  </tr>
  <tr>
    <td>init</td>
    <td>string</td>
    <td>Date/time of the original instantiation of this ad (i.e., this object or any of its children) in the format of ISO-8601; W3C profile.  Refer to www.w3.org/TR/NOTE-datetime.</td>
  </tr>
  <tr>
    <td>lastmod</td>
    <td>string</td>
    <td>Date/time of most recent modification to this ad (i.e., this object or any of its children other than the "Audit" object) in the format of ISO-8601; W3C profile.  Refer to www.w3.org/TR/NOTE-datetime.</td>
  </tr>
  <tr>
    <td>display</td>
    <td>Object; required *</td>
    <td>"Media Subtype Object" that indicates this is a display ad and provides additional detail as such.  Refer to Object:  Display.
* Required if no other media subtype object is specified.</td>
  </tr>
  <tr>
    <td>video</td>
    <td>object; required *</td>
    <td>"Media Subtype Object" that indicates this is a video ad and provides additional detail as such.  Refer to Object:  Video.
* Required if no other media subtype object is specified.</td>
  </tr>
  <tr>
    <td>audio</td>
    <td>object; required *</td>
    <td>"Media Subtype Object" that indicates this is an audio ad and provides additional detail as such.  Refer to Object:  Audio.
* Required if no other media subtype object is specified.</td>
  </tr>
  <tr>
    <td>audit</td>
    <td>object</td>
    <td>An object depicting the audit status of the ad; typically part of a quality/safety review process.  Refer to Object:  Audit.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Display <a name="object_display"></a>

This object provides additional detail about an ad specifically for display ads. There are multiple attributes for specifying creative details: "`banner`" for simple banner images "`native`" for native ads, "`adm`" for including general markup, and "`curl`" for referencing general markup via URL. In any given "`Display`" object, only one of these attributes should be used to avoid confusion. To the extent feasible, structured objects should be favored over general markup for quality and safety issues.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string</td>
    <td>Mime type of the ad (e.g., "image/jpeg").</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>API required by the ad if applicable.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer</td>
    <td>Subtype of display creative.  Refer to List:  Creative Subtypes - Display.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Absolute width of the creative in device independent pixels (DIPS), typically for non-native ads.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Absolute height of the creative in device independent pixels (DIPS), typically for non-native ads.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>wratio</td>
    <td>integer</td>
    <td>Relative width of the creative when expressing size as a ratio, typically for non-native ads.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>hratio</td>
    <td>integer</td>
    <td>Relative height of the creative when expressing size as a ratio, typically for non-native ads.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>priv</td>
    <td>string</td>
    <td>URL of a page informing the user about a buyer's targeting activity.</td>
  </tr>
  <tr>
    <td>adm</td>
    <td>string</td>
    <td>General display markup (e.g., HTML, AMPHTML) if not using a structured alternative (e.g., "banner", "native").
Note that including both "adm" and "curl" is not recommended.</td>
  </tr>
  <tr>
    <td>curl</td>
    <td>string</td>
    <td>Optional means of retrieving display markup by reference; a URL that can return HTML, AMPHTML, or a collection native "Asset" object and their subordinates).  If this ad is matched to a Placement specification, the "Placement.curlx" attribute indicates if this markup retrieval option is supported.
Note that including both "adm" and "curl" is not recommended. </td>
  </tr>
  <tr>
    <td>banner</td>
    <td>object</td>
    <td>Structured banner image object, recommended for simple banner creatives.  Refer to Object:  Banner.</td>
  </tr>
  <tr>
    <td>native</td>
    <td>object</td>
    <td>Structured native object, recommended for native ads.  Refer to Object:  Native.</td>
  </tr>
  <tr>
    <td>event</td>
    <td>object array</td>
    <td>Array of events that the advertiser or buying platform wants to track.  Refer to  Object:  Event.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Banner <a name="object_banner"></a>

This object describes a basic banner creative.  It is intended for display scenarios that require a simple, structured image/link pair and is more secure than allowing arbitrary HTML or JavaScript code.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>img</td>
    <td>string; required</td>
    <td>A URL that will return the image.</td>
  </tr>
  <tr>
    <td>link</td>
    <td>object</td>
    <td>Destination link if the image is activated (e.g., clicked); not applicable in some contexts (e.g., DOOH) and its inclusion does not guarantee it will be supported.  Refer to Object:  LinkAsset.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Native <a name="object_native"></a>

This object is the root of a structure that defines a native display ad.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>link</td>
    <td>object</td>
    <td>Default destination link for the native ad overall; used if an asset is activated (e.g., clicked) that doesn't specify it's own destination link.  Refer to Object:  LinkAsset.</td>
  </tr>
  <tr>
    <td>asset</td>
    <td>object array</td>
    <td>Array of assets that comprise the native ad.  Refer to Object:  Asset.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Asset <a name="object_asset"></a>

This object is the container for each asset comprising a native ad.  Each asset is of a specific type and to reflect this, one and only one of the subtype objects (i.e., "`title`", "`img`", "`video`", "`data`") must be present; all others should be omitted.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>integer</td>
    <td>The value of "AssetFormat.id" if this ad references a specific native placement defined by a "Placement" object and its structure.</td>
  </tr>
  <tr>
    <td>req</td>
    <td>Integer; default 0</td>
    <td>Indicates if the asset is required to be displayed, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>title</td>
    <td>object; required *</td>
    <td>"Asset Subtype Object" that indicates this is a title asset and provides additional detail as such.  Refer to Object:  TitleAsset.
* Required if no other asset subtype object is specified.</td>
  </tr>
  <tr>
    <td>image</td>
    <td>object; required *</td>
    <td>"Asset Subtype Object" that indicates this is an image asset and provides additional detail as such.  Refer to Object:  ImageAsset.
* Required if no other asset subtype object is specified.</td>
  </tr>
  <tr>
    <td>video</td>
    <td>object; required *</td>
    <td>"Asset Subtype Object" that indicates this is a video asset and provides additional detail as such.  Refer to Object:  VideoAsset.
* Required if no other asset subtype object is specified.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>object; required *</td>
    <td>"Asset Subtype Object" that indicates this is a data asset and provides additional detail as such.  Refer to Object:  DataAsset.
* Required if no other asset subtype object is specified.</td>
  </tr>
  <tr>
    <td>link</td>
    <td>object; required *</td>
    <td>"Asset Subtype Object" that indicates this is a link asset and provides additional detail as such.  Refer to Object:  LinkAsset.
* Required if no other asset subtype object is specified.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  LinkAsset <a name="object_linkasset"></a>

This object identifies the native asset as a link asset and is used to define navigation for *call-to-action* or other activations (i.e., clicks).  A link asset can be independent or associated with the overall native ad (i.e., a default for all assets).

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>url</td>
    <td>string; required</td>
    <td>Landing URL of the clickable link.</td>
  </tr>
  <tr>
    <td>urlfb</td>
    <td>string</td>
    <td>Fallback URL for deep-link to be used if the URL specified in "url" is not supported by the device.</td>
  </tr>
  <tr>
    <td>trkr</td>
    <td>string array</td>
    <td>List of third-party tracker URLs to be fired on click.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  TitleAsset <a name="object_titleasset"></a>

This object identifies the native asset as a title asset, which is essentially just a plain text string with specified length.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>text</td>
    <td>string; required</td>
    <td>The text content of the text element.</td>
  </tr>
  <tr>
    <td>len</td>
    <td>integer</td>
    <td>The length of the contents of the "text" attribute.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  ImageAsset <a name="object_imageasset"></a>

This object identifies the native asset as a image asset.  Image assets are use for such elements as the actual creative images and icons.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>url</td>
    <td>string; required</td>
    <td>A URL that returns the image for the asset.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer; recommended</td>
    <td>Width of the image asset in device independent pixels (DIPS).</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer; recommended</td>
    <td>Height of the image asset in device independent pixels (DIPS).</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer</td>
    <td>The type of image represented by this asset.  Refer to List:  Native Image Asset Types.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  VideoAsset <a name="object_videoasset"></a>

This object identifies the native asset as a video asset.  Video markup (e.g., VAST) must be either included or referenced.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>adm</td>
    <td>string; required *</td>
    <td>Video markup (e.g., VAST document) for the asset.
* Exactly one of "adm" and "curl" is required.  Including both is not recommended.  </td>
  </tr>
  <tr>
    <td>curl</td>
    <td>string; required *</td>
    <td>A URL that returns the video markup (e.g., VAST document) for the asset.  If this ad is matched to a placement specification, the "Placement.curlx" attribute indicates if this markup retrieval option is supported.
* Exactly one of "adm" and "curl" is required.  Including both is not recommended.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  DataAsset <a name="object_dataasset"></a>

This object identifies the native asset as a data asset.  A data asset is used for all miscellaneous elements such as brand name, ratings, stars, review count, downloads, price, counts, etc.  It is purposefully generic to support native elements not currently contemplated by this specification.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>value</td>
    <td>string; required</td>
    <td>A formatted string of data to be displayed (e.g., "5 stars", "3.4 stars out of 5", "$ 10", etc.).</td>
  </tr>
  <tr>
    <td>len</td>
    <td>integer</td>
    <td>The length of the "`value`" contents.  This length should conform to recommendations provided in List:  Native Data Asset Types, where applicable.</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer</td>
    <td>The type of data represented by this asset.  Refer to List:  Native Data Asset Types.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Event <a name="object_event"></a>

This object specifies a type of event that the advertiser or buying platform wants to track along with the information required to do so.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer; required</td>
    <td>Type of event to track.  Refer to List:  Event Types.</td>
  </tr>
  <tr>
    <td>method</td>
    <td>integer; required</td>
    <td>Method of tracking requested.  Refer to List:  Event Tracking Methods.</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>The APIs being used by the tracker; only relevant when the tracking method is JavaScript.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>url</td>
    <td>string; required *</td>
    <td>The URL of the tracking pixel or JavaScript tag, respectively.
* Required for Image-Pixel or JavaScript methods.</td>
  </tr>
  <tr>
    <td>cdata</td>
    <td>object (Map)</td>
    <td>An array of key-value pairs to support vendor-specific data required for custom tracking.  For example, the account number of a buyer with a tracking company might be represented as:  {"acct": "123"}.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Video <a name="object_video"></a>

This object provides additional detail about an ad specifically for video ads.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array</td>
    <td>Mime type(s) of the ad creative(s) (e.g., "video/mp4").</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>API required by the ad if applicable.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer</td>
    <td>Subtype of video creative.  Refer to List:  Creative Subtypes - Video.</td>
  </tr>
  <tr>
    <td>dur</td>
    <td>integer</td>
    <td>Duration of the video creative in seconds.</td>
  </tr>
  <tr>
    <td>adm</td>
    <td>string</td>
    <td>Video markup (e.g., VAST).
Note that including both "adm" and "curl" is not recommended.</td>
  </tr>
  <tr>
    <td>curl</td>
    <td>string</td>
    <td>Optional means of retrieving markup by reference; a URL that returns video markup (e.g., VAST).  If this ad is matched to a Placement specification, the "Placement.curlx" attribute indicates if this markup retrieval option is supported.
Note that including both "adm" and "curl" is not recommended. </td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Audio <a name="object_audio"></a>

This object provides additional detail about an ad specifically for audio ads.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array</td>
    <td>Mime type(s) of the ad creative(s) (e.g., "audio/mp4").</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>API required by the ad if applicable.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer</td>
    <td>Subtype of audio creative.  Refer to List:  Creative Subtypes - Audio.</td>
  </tr>
  <tr>
    <td>dur</td>
    <td>integer</td>
    <td>Duration of the audio creative in seconds.</td>
  </tr>
  <tr>
    <td>adm</td>
    <td>string</td>
    <td>Audio markup (e.g., DAAST).
Note that including both "adm" and "curl" is not recommended.</td>
  </tr>
  <tr>
    <td>curl</td>
    <td>string</td>
    <td>Optional means of retrieving markup by reference; a URL that returns audio markup (e.g., DAAST).  If this ad is matched to a Placement specification, the "Placement.curlx" attribute indicates if this markup retrieval option is supported.
Note that including both "adm" and "curl" is not recommended. </td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Audit <a name="object_audit"></a>

This objects represents the outcome of some form of review of the ad.  This is typical, for example, when scanning for malware or otherwise performing ad quality reviews.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>status</td>
    <td>Integer</td>
    <td>The audit status of the ad.  Refer to List:  Audit Status Codes.</td>
  </tr>
  <tr>
    <td>feedback</td>
    <td>string array</td>
    <td>One or more human-readable explanations as to reasons for rejection or any changes to fields for ad quality reasons (e.g., "adomain", "cat", "attr", etc.).</td>
  </tr>
  <tr>
    <td>init</td>
    <td>string</td>
    <td>Date/time of the original instantiation of this object in the format of ISO-8601; W3C profile.  Refer to www.w3.org/TR/NOTE-datetime.</td>
  </tr>
  <tr>
    <td>lastmod</td>
    <td>string</td>
    <td>Date/time of most recent modification to this object in the format of ISO-8601; W3C profile.  Refer to www.w3.org/TR/NOTE-datetime.</td>
  </tr>
  <tr>
    <td>corr</td>
    <td>object</td>
    <td>Correction object wherein the auditor can specify changes to attributes of the "Ad" object or its children they believe to be proper.  For example, if the original "Ad" indicated a category of "IAB3", but the auditor deems the correct category to be "IAB13", then "corr" could include a sparse "Ad" object including just the "cat" array indicating "IAB13".</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


## Placement Objects <a name="placementobjects"></a>

The Placement group includes objects that define the set of allowed ads for a given impression. This can include mechanical information (e.g., sizes, supported mime types and other rendering options), placement details and positioning, various restrictions lists (e.g., advertiser domains, content categories), and more.

The following figure presents the objects and interrelationships in this group. The objects are defined in the subsections thereafter.

![](https://drive.google.com/uc?id=1W6YPuUGORP9Hf33nlKhmfY_ISE4MQCLA)

### Object:  Placement <a name="object_placement"></a>

This object represents the properties of a placement and the characteristics of ads permitted to be rendering within them.  Placements of all types begin with this object as their root.  It contains one or more subtype objects (i.e., "`display`", "`video`", "`audio`") that define the kinds of media permitted as well as media specific placement behaviors.

The other attributes in this object apply to all aspects and substructures of the placement (i.e., the same language, secure status, etc. apply to all media types and native assets as applicable).

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>tagid</td>
    <td>string</td>
    <td>Identifier for specific ad placement or ad tag; unique within a distribution channel.</td>
  </tr>
  <tr>
    <td>ssai</td>
    <td>Integer; default 0</td>
    <td>Indicates if server-side ad insertion (e.g., stitching an ad into an audio or video stream) is in use and the impact of this on asset and tracker retrieval, where 0 = status unknown, 1 = all client-side (i.e., not server-side), 2 = assets stitched server-side but tracking pixels fired client-side, 3 = all server-side.</td>
  </tr>
  <tr>
    <td>sdk</td>
    <td>string</td>
    <td>Name of ad mediation partner, SDK technology, or player responsible for rendering ad (typically video, audio, or mobile); used by some ad servers to customize ad code by partner.</td>
  </tr>
  <tr>
    <td>sdkver</td>
    <td>string</td>
    <td>Version of the SDK specified in the "sdk" attribute.</td>
  </tr>
  <tr>
    <td>reward</td>
    <td>integer; default 0</td>
    <td>Indicates if this is a rewarded placement, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>wlang</td>
    <td>string array</td>
    <td>Whitelist of permitted languages of the creative using ISO-639-1-alpha-2.  In practice, vendors using this object may elect an alternate standard (e.g., BCP-47) in which case this must be communicated a priori.  Omission of this attribute indicates there are no restrictions.</td>
  </tr>
  <tr>
    <td>secure</td>
    <td>integer</td>
    <td>Flag to indicate if the creative is secure (i.e., uses HTTPS for all assets and markup), where 0 = no, 1 = yes.  There is no default and thus if omitted, the secure state is unknown.  However, as a practical matter, the safe assumption is to treat unknown as non-secure.</td>
  </tr>
  <tr>
    <td>admx</td>
    <td>integer</td>
    <td>Indicates if including markup is supported (i.e., the various "adm" attributes throughout the "Placement" structure), where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>curlx</td>
    <td>integer</td>
    <td>Indicates if retrieving markup via URL reference is supported (i.e., the various "curl" attributes throughout the "Placement" structure), where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>display</td>
    <td>object; required *</td>
    <td>"Placement Subtype Object" that indicates that this may be a display placement and provides additional detail related thereto.  Refer to Object:  DisplayPlacement.
* At least one placement subtype object is required.</td>
  </tr>
  <tr>
    <td>video</td>
    <td>object; required *</td>
    <td>"Placement Subtype Object" that indicates that this may be a video placement and provides additional detail related thereto.  Refer to Object:  VideoPlacement.
* At least one placement subtype object is required.</td>
  </tr>
  <tr>
    <td>audio</td>
    <td>object; required *</td>
    <td>"Placement Subtype Object" that indicates that this may be an audio placement and provides additional detail related thereto.  Refer to Object:  AudioPlacement.
* At least one placement subtype object is required.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  DisplayPlacement <a name="object_displayplacement"></a>

This object signals that the placement may be a display placement.  It provides additional detail about permitted display ads including simple banners, AMPHTML (i.e., Accelerated Mobile Pages), and native.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>pos</td>
    <td>integer</td>
    <td>Placement position on screen.  Refer to List:  Placement Positions.</td>
  </tr>
  <tr>
    <td>instl</td>
    <td>integer; default 0</td>
    <td>Indicates if this is an interstitial placement, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>topframe</td>
    <td>integer</td>
    <td>Indicates if the placement will be loaded into an iframe or not, where 0 = unfriendly iframe or unknown, 1 = top frame,  friendly iframe, or SafeFrame.  A value of "1" can be understood to mean that expandable ads are technically capable of being delivered.</td>
  </tr>
  <tr>
    <td>ifrbust</td>
    <td>string array</td>
    <td>Array of iframe busters supported by this placement.  The meaning of strings in this attribute must be coordinated a priori among vendors.</td>
  </tr>
  <tr>
    <td>clktype</td>
    <td>integer; default 1</td>
    <td>Indicates the click type of this placement.  Refer to List:  Click Types.</td>
  </tr>
  <tr>
    <td>ampren</td>
    <td>integer</td>
    <td>AMPHTML rendering treatment for AMP ads in this placement, where 1 = early loading, 2 = standard loading.</td>
  </tr>
  <tr>
    <td>ptype</td>
    <td>Integer; recommended</td>
    <td>The display placement type.  Refer to List:  Display Placement Types.</td>
  </tr>
  <tr>
    <td>context</td>
    <td>integer; recommended</td>
    <td>The context of the placement.  Refer to List:  Display Context Types.</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array</td>
    <td>Array of supported mime types (e.g., "image/jpeg", "image/gif").  If omitted, all types are assumed.</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>List of supported APIs.  If an API is not explicitly listed, it is assumed to be unsupported.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer array</td>
    <td>Creative subtypes permitted.  Refer to List:  Creative Subtypes - Display.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Width of the placement in units specified by "unit".  Note that this size applies to the placement itself; permitted creative sizes are specified elsewhere (e.g., "DisplayFormat", "ImageAssetFormat", etc.).</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Width of the placement in units specified by "unit".  Note that this size applies to the placement itself; permitted creative sizes are specified elsewhere (e.g., "DisplayFormat", "ImageAssetFormat", etc.).</td>
  </tr>
  <tr>
    <td>unit</td>
    <td>integer; default 1</td>
    <td>Unit of size used for placement size (i.e., "w" and "h" attributes).  Refer to List:  Size Units.</td>
  </tr>
  <tr>
    <td>displayfmt</td>
    <td>object array</td>
    <td>Array of objects that govern the attributes (e.g., sizes) of a banner display placement.  Refer to Object:  DisplayFormat.</td>
  </tr>
  <tr>
    <td>nativefmt</td>
    <td>object</td>
    <td>This object specified the required and permitted assets and attributes of a native display placement.  Refer to Object:  NativeFormat.</td>
  </tr>
  <tr>
    <td>event</td>
    <td>object array</td>
    <td>Array of supported ad tracking events.  Refer to Object:  EventSpec.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  DisplayFormat <a name="object_displayformat"></a>

This object represents an allowed set of parameters for a banner display ad and often appears as an array when multiple sizes are permitted.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Absolute width of the creative in units specified by "DisplayPlacement.unit".
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Absolute height of the creative in units specified by "DisplayPlacement.unit".
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>wratio</td>
    <td>integer</td>
    <td>Relative width of the creative when expressing size as a ratio.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>hratio</td>
    <td>integer</td>
    <td>Relative height of the creative when expressing size as a ratio.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>expdir</td>
    <td>integer array</td>
    <td>Directions in which the creative is permitted to expand.  Refer to List:  Expandable Directions.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  NativeFormat <a name="object_nativeformat"></a>

This object refines a display placement to be specifically a native display placement.  It serves as the root of a structure that includes the specifications for each of the assets that comprise the native placement.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>priv</td>
    <td>integer; default 0</td>
    <td>Indicator of whether or not the placement supports a buyer-specific privacy notice URL, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>asset</td>
    <td>array of objects; required</td>
    <td>Array of objects that specify the set of native assets and their permitted formats.  Refer to Object:  AssetFormat.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  AssetFormat <a name="object_assetformat"></a>

This object represents the permitted specifications of a single asset of a native ad.  Along with its own attributes, exactly one of the asset subtype objects must be included.  All others must be omitted.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>integer; required</td>
    <td>Asset ID, unique within the scope of this placement specification.</td>
  </tr>
  <tr>
    <td>req</td>
    <td>integer; default 0</td>
    <td>Indicator of whether or not this asset is required, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>title</td>
    <td>object; required *</td>
    <td>"Asset Format Subtype Object" that indicates this is specifying a title asset and provides additional detail as such.  Refer to Object:  TitleAssetFormat.
* Required if no other asset format subtype object is specified.</td>
  </tr>
  <tr>
    <td>img</td>
    <td>object; required *</td>
    <td>"Asset Format Subtype Object" that indicates this is specifying an image asset and provides additional detail as such.  Refer to Object:  ImageAssetFormat.
* Required if no other asset format subtype object is specified.</td>
  </tr>
  <tr>
    <td>video</td>
    <td>object; required *</td>
    <td>"Asset Format Subtype Object", which leverages the "VideoPlacement" object, that indicates this is specifying a video asset and provides additional detail as such.  Refer to Object:  VideoPlacement.
* Required if no other asset format subtype object is specified.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>object; required *</td>
    <td>"Asset Format Subtype Object" that indicates this is specifying a data asset and provides additional detail as such.  Refer to Object:  DataAssetFormat.
* Required if no other asset format subtype object is specified.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  TitleAssetFormat <a name="object_titleassetformat"></a>

This object is used to provide native asset format specifications for a title element.  Title elements are simple strings.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>len</td>
    <td>integer; required</td>
    <td>The maximum allowed length of the title value.  Recommended lengths are 25, 90, or 140.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  ImageAssetFormat <a name="object_imageassetformat"></a>

This object is used to provide native asset format specifications for an image element.  Image elements are typically used for the actual creative image and icons.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer</td>
    <td>The type of image asset supported.  Refer to  List:  Native Image Asset Types.</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array</td>
    <td>Array of supported mime types (e.g., "image/jpeg", "image/gif").  If omitted, all types are assumed.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Absolute width of the image asset in device independent pixels (DIPS).
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Absolute height of the image asset in device independent pixels (DIPS).
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>wmin</td>
    <td>integer</td>
    <td>The minimum requested absolute width of the image in device independent pixels (DIPS).  This option should be used for any scaling of images by the client.</td>
  </tr>
  <tr>
    <td>hmin</td>
    <td>integer</td>
    <td>The minimum requested absolute height of the image in device independent pixels (DIPS).  This option should be used for any scaling of images by the client.</td>
  </tr>
  <tr>
    <td>wratio</td>
    <td>integer</td>
    <td>Relative width of the image asset when expressing size as a ratio.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>hratio</td>
    <td>integer</td>
    <td>Relative height of the image asset when expressing size as a ratio.
Note that mixing absolute and relative sizes is not recommended.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  DataAssetFormat <a name="object_dataassetformat"></a>

This object is used to provide native asset format specifications for a data element.  A data asset is used for all miscellaneous elements such as brand name, ratings, stars, review count, downloads, prices, etc.  It is purposefully generic to support native elements not currently contemplated by this specification.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer; required</td>
    <td>The type of data asset supported.  Refer to List:  Native Data Asset Types.</td>
  </tr>
  <tr>
    <td>len</td>
    <td>integer</td>
    <td>The maximum allowed length of the data value.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  EventSpec <a name="object_eventspec"></a>

This object specifies a type of ad tracking event and which methods of tracking are available for it.  This object may appear as an array for a given placement indicating various types of available tracking events.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer; required</td>
    <td>Type of supported ad tracking event.  Refer to List:  Event Types.</td>
  </tr>
  <tr>
    <td>method</td>
    <td>integer array</td>
    <td>Array of supported event tracking methods for this event type.  Refer to List:  Event Tracking Methods.</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>Event tracking APIs available for use; only relevant for JavaScript method trackers.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>jstrk</td>
    <td>string array</td>
    <td>Array of domains, top two levels only (e.g., "tracker.com"), that constitute a restriction list of JavaScript trackers.  The sense of the restrictions is determined by "wjs".</td>
  </tr>
  <tr>
    <td>wjs</td>
    <td>integer; default 1</td>
    <td>Sense of the "jstrk" restriction list, where 0 = block list, 1 = whitelist.</td>
  </tr>
  <tr>
    <td>pxtrk</td>
    <td>string array</td>
    <td>Array of domains, top two levels only (e.g., "tracker.com"), that constitute a restriction list of pixel image trackers.  The sense of the restrictions is determined by "wpx".</td>
  </tr>
  <tr>
    <td>wpx</td>
    <td>integer; default 1</td>
    <td>Sense of the "pxtrk" restriction list, where 0 = block list, 1 = whitelist.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  VideoPlacement <a name="object_videoplacement"></a>

This object signals that the placement may be a video placement and provides additional detail about permitted video ads (e.g., VAST).

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>ptype</td>
    <td>integer</td>
    <td>Placement subtype.  Refer to List:  Placement Subtypes - Video.</td>
  </tr>
  <tr>
    <td>pos</td>
    <td>integer</td>
    <td>Placement position on screen.  Refer to List:  Placement Positions.</td>
  </tr>
  <tr>
    <td>delay</td>
    <td>integer</td>
    <td>Indicates the start delay in seconds for pre-roll, mid-roll, or post-roll placements.  For additional generic values, refer to List:  Start Delay Modes.</td>
  </tr>
  <tr>
    <td>skip</td>
    <td>integer</td>
    <td>Indicates if the placement imposes ad skippability, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>skipmin</td>
    <td>integer; default 0</td>
    <td>The placement allows creatives of total duration greater than this number of seconds to be skipped; only applicable if the ad is skippable.</td>
  </tr>
  <tr>
    <td>skipafter</td>
    <td>integer; default 0</td>
    <td>Number of seconds a creative must play before the placement enables skipping; only applicable if the ad is skippable.</td>
  </tr>
  <tr>
    <td>playmethod</td>
    <td>integer</td>
    <td>Playback method in use for this placement.  Refer to List:  Playback Methods.</td>
  </tr>
  <tr>
    <td>playend</td>
    <td>integer</td>
    <td>The event that causes playback to end for this placement.  Refer to List:  Playback Cessation Modes.</td>
  </tr>
  <tr>
    <td>clktype</td>
    <td>integer</td>
    <td>Indicates the click type of the placement.  Refer to List:  Click Types.</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array; required</td>
    <td>Array of supported mime types (e.g., "video/mp4").  If omitted, all types are assumed.</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>List of supported APIs for this placement.  If an API is not explicitly listed, it is assumed to be unsupported.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer array</td>
    <td>Creative subtypes permitted for this placement.  Refer to List:  Creative Subtypes - Video.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Width of the creative in units specified by "unit".</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Height of the creative in units specified by "unit".</td>
  </tr>
  <tr>
    <td>unit</td>
    <td>integer; default 1</td>
    <td>Units of size used for "w" and "h" attributes.  Refer to List:  Size Units.</td>
  </tr>
  <tr>
    <td>mindur</td>
    <td>integer</td>
    <td>Minimum creative duration in seconds.</td>
  </tr>
  <tr>
    <td>maxdur</td>
    <td>integer</td>
    <td>Maximum creative duration in seconds.</td>
  </tr>
  <tr>
    <td>maxext</td>
    <td>Integer; default 0</td>
    <td>Maximum extended creative duration if extension is allowed.  If 0, extension is not allowed.  If -1, extension is allowed and there is no time limit imposed.  If greater than 0, then the value represents the number of seconds of extended play supported beyond the "maxdur" value.</td>
  </tr>
  <tr>
    <td>minbitr</td>
    <td>integer</td>
    <td>Minimum bit rate of the creative in Kbps.</td>
  </tr>
  <tr>
    <td>maxbitr</td>
    <td>integer</td>
    <td>Maximum bit rate of the creative in Kbps.</td>
  </tr>
  <tr>
    <td>delivery</td>
    <td>integer array</td>
    <td>Array of supported creative delivery methods.  If omitted, all can be assumed.  Refer to List:  Delivery Methods.</td>
  </tr>
  <tr>
    <td>maxseq</td>
    <td>integer</td>
    <td>The maximum number of ads that can be played in an ad pod.</td>
  </tr>
  <tr>
    <td>linear</td>
    <td>integer</td>
    <td>Indicates if the creative must be linear, nonlinear, etc.  If none specified, no restrictions are assumed.  Refer to List:  Linearity Modes.</td>
  </tr>
  <tr>
    <td>boxing</td>
    <td>integer; default 1</td>
    <td>Indicates if letterboxing of 4:3 creatives into a 16:9 window is allowed, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>comp</td>
    <td>object array</td>
    <td>Array of objects indicating that companion ads are available and providing the specifications thereof.  Refer to Object:  Companion.</td>
  </tr>
  <tr>
    <td>comptype</td>
    <td>integer array</td>
    <td>Supported companion ad types; recommended if companion ads are specified in "comp".  Refer to List:  Companion Types.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  AudioPlacement <a name="object_audioplacement"></a>

This object signals that the placement may be an audio placement and provides additional detail about permitted audio ads (e.g., DAAST).

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>delay</td>
    <td>integer</td>
    <td>Indicates the start delay in seconds for pre-roll, mid-roll, or post-roll placements.  For additional generic values, refer to List:  Start Delay Modes.</td>
  </tr>
  <tr>
    <td>skip</td>
    <td>integer</td>
    <td>Indicates if the placement imposes ad skippability, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>skipmin</td>
    <td>integer; default 0</td>
    <td>The placement allows creatives of total duration greater than this number of seconds to be skipped; only applicable if the ad is skippable.</td>
  </tr>
  <tr>
    <td>skipafter</td>
    <td>integer; default 0</td>
    <td>Number of seconds a creative must play before the placement enables skipping; only applicable if the ad is skippable.</td>
  </tr>
  <tr>
    <td>playmethod</td>
    <td>integer</td>
    <td>Playback method in use for this placement.  Refer to List:  Playback Methods.</td>
  </tr>
  <tr>
    <td>playend</td>
    <td>integer</td>
    <td>The event that causes playback to end for this placement.  Refer to List:  Playback Cessation Modes.</td>
  </tr>
  <tr>
    <td>feed</td>
    <td>integer</td>
    <td>Type of audio feed of this placement.  Refer to List:  Feed Types.</td>
  </tr>
  <tr>
    <td>nvol</td>
    <td>integer</td>
    <td>Volume normalization mode of this placement.  Refer to List:  Volume Normalization Modes.</td>
  </tr>
  <tr>
    <td>mime</td>
    <td>string array; required</td>
    <td>Array of supported mime types (e.g., "audio/mp4").  If omitted, all types are assumed.</td>
  </tr>
  <tr>
    <td>api</td>
    <td>integer array</td>
    <td>List of supported APIs for this placement.  If an API is not explicitly listed, it is assumed to be unsupported.  Refer to List:  API Frameworks.</td>
  </tr>
  <tr>
    <td>ctype</td>
    <td>integer array</td>
    <td>Creative subtypes permitted for this placement.  Refer to List:  Creative Subtypes - Audio.</td>
  </tr>
  <tr>
    <td>mindur</td>
    <td>integer</td>
    <td>Minimum creative duration in seconds.</td>
  </tr>
  <tr>
    <td>maxdur</td>
    <td>integer</td>
    <td>Maximum creative duration in seconds.</td>
  </tr>
  <tr>
    <td>maxext</td>
    <td>integer</td>
    <td>Maximum extended creative duration if extension is allowed.  If 0, extension is not allowed.  If -1, extension is allowed and there is no time limit imposed.  If greater than 0, then the value represents the number of seconds of extended play supported beyond the "maxdur" value.</td>
  </tr>
  <tr>
    <td>minbitr</td>
    <td>integer</td>
    <td>Minimum bit rate of the creative in Kbps.</td>
  </tr>
  <tr>
    <td>maxbitr</td>
    <td>integer</td>
    <td>Maximum bit rate of the creative in Kbps.</td>
  </tr>
  <tr>
    <td>delivery</td>
    <td>integer array</td>
    <td>Array of supported creative delivery methods.  If omitted, all can be assumed.  Refer to List:  Delivery Methods.</td>
  </tr>
  <tr>
    <td>maxseq</td>
    <td>integer</td>
    <td>The maximum number of ads that can be played in an ad pod.</td>
  </tr>
  <tr>
    <td>comp</td>
    <td>object array</td>
    <td>Array of objects indicating that companion ads are available and providing the specifications thereof.  Refer to Object:  Companion.</td>
  </tr>
  <tr>
    <td>comptype</td>
    <td>integer array</td>
    <td>Supported companion ad types; recommended if companion ads are specified in "comp".  Refer to List:  Companion Types.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Companion <a name="object_companion"></a>

This object is used in video and audio placements to specify an associated or so-called *companion* display ad.  Video and audio placements can specify an array of companion ads.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string</td>
    <td>Identifier of the companion ad; unique within this placement.</td>
  </tr>
  <tr>
    <td>vcm</td>
    <td>integer</td>
    <td>Indicates the companion ad rendering mode relative to the associated video or audio ad, where 0 = concurrent, 1 = end-card.  For a given placement, typically only one companion at most should be designated as an end card.</td>
  </tr>
  <tr>
    <td>display</td>
    <td>object</td>
    <td>Display specification object representing the companion ad.  Refer to Object:  DisplayPlacement.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


## Context Objects <a name="contextobjects"></a>

This group of objects represent concepts that are interacting, presenting, enclosing, or are otherwise relating to the world in which impressions live. These include the user, their device, their location, the channel (e.g., site, app, digital out-of-home) with which they are interacting, the channel's publisher, its content, and any regulations that are in effect (e.g., COPPA, GDPR).

The following figure presents the objects and interrelationships in this group. The objects are defined in the subsections thereafter.

![](https://drive.google.com/open?id=1si55OMpfqweHwCbZ17Da3U95V5NO0XbA)

### Abstract Class:  DistributionChannel <a name="abstract_distributionchannel"></a>

A distribution channel is an abstraction of the various types of entities or channels through which ads are distributed.  Examples include websites, mobile apps, and digital out-of-home (DOOH) systems.  This generalized class contains those attributes and relationships that are common to all distribution channels and as such, all of its attributes and relationships are inherited by each of its derived classes.

Note:  As an abstract class, a DistributionChannel is never instantiated on its own.  Only objects of its derived classes are actually realized.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string; recommended</td>
    <td>Vendor-specific unique identifier of the distribution channel.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Displayable name of the distribution channel.</td>
  </tr>
  <tr>
    <td>pub</td>
    <td>object</td>
    <td>Details about the publisher of the distribution channel.  Refer to  Object:  Publisher.</td>
  </tr>
  <tr>
    <td>content</td>
    <td>object</td>
    <td>Details about the content within the distribution channel.  Refer to Object:  Content.</td>
  </tr>
</table>


### Object:  Site <a name="object_site"></a>

*Derived from:* [DistributionChannel](#abstract_distributionchannel)

This object is used to define an ad supported website, in contrast to a non-browser application, for example. As a derived class, a "`Site`" object inherits all "`DistributionChannel`" attributes and adds those defined below.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>domain</td>
    <td>string</td>
    <td>Domain of the site (e.g., "mysite.foo.com").</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories describing the site using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>sectcat</td>
    <td>string array</td>
    <td>Array of content categories describing the current section of the site using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>pagecat</td>
    <td>string array</td>
    <td>Array of content categories describing the current page or view of the site using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer</td>
    <td>The taxonomy in use for the "cat", "sectcat" and "pagecat" attributes.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>privpolicy</td>
    <td>integer</td>
    <td>Indicates if the site has a privacy policy, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>keywords</td>
    <td>string</td>
    <td>Comma separated list of keywords about the site.</td>
  </tr>
  <tr>
    <td>page</td>
    <td>string</td>
    <td>URL of the page within the site.</td>
  </tr>
  <tr>
    <td>ref</td>
    <td>string</td>
    <td>Referrer URL that caused navigation to the current page.</td>
  </tr>
  <tr>
    <td>search</td>
    <td>string</td>
    <td>Search string that caused navigation to the current page.</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>integer</td>
    <td>Indicates if the site has been programmed to optimize layout when viewed on mobile devices, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>amp</td>
    <td>integer</td>
    <td>Indicates if the page is built with AMP HTML, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  App <a name="object_app"></a>

*Derived from:* [DistributionChannel](#abstract_distributionchannel)

This object is used to define an ad supported non-browser application, in contrast to a typical website, example. As a derived class, an "`App`" object inherits all "`DistributionChannel`" attributes and adds those defined below.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>domain</td>
    <td>string</td>
    <td>Domain of the app (e.g., "mygame.foo.com").</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories describing the app using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>sectcat</td>
    <td>string array</td>
    <td>Array of content categories describing the current section of the app using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>pagecat</td>
    <td>string array</td>
    <td>Array of content categories describing the current page or view of the app using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer</td>
    <td>The taxonomy in use for the "cat", "sectcat" and "pagecat" attributes.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>privpolicy</td>
    <td>integer</td>
    <td>Indicates if the app has a privacy policy, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>keywords</td>
    <td>string</td>
    <td>Comma separated list of keywords about the app.</td>
  </tr>
  <tr>
    <td>bundle</td>
    <td>string</td>
    <td>Bundle or package name of the app (e.g., "com.foo.mygame") and should NOT be app store IDs (e.g., not iTunes store IDs).</td>
  </tr>
  <tr>
    <td>storeid</td>
    <td>string</td>
    <td>The ID of the app in an app store (e.g., Apple iTunes, Google Play).</td>
  </tr>
  <tr>
    <td>storeurl</td>
    <td>string</td>
    <td>App store URL for an installed app; for IQG 2.1 compliance.</td>
  </tr>
  <tr>
    <td>ver</td>
    <td>string</td>
    <td>Application version.</td>
  </tr>
  <tr>
    <td>paid</td>
    <td>Integer; default 0</td>
    <td>Indicator of whether or not this is a paid app, where 0 = free, 1 = paid.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Dooh <a name="object_dooh"></a>

*Derived from:* [DistributionChannel](#abstract_distributionchannel)

This object is used to define an ad supported digital out-of-home (DOOH) experience such as a public kiosk or digital billboard. As a derived class, a "`Dooh`" object inherits all "`DistributionChannel`" attributes and adds those defined below.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>venue</td>
    <td>integer</td>
    <td>The type of out-of-home venue.  Refer to List:  DOOH Venue Types.</td>
  </tr>
  <tr>
    <td>fixed</td>
    <td>integer</td>
    <td>Indicates whether the DOOH placement is in a fixed location (e.g., kiosk, billboard, elevator) or is movable (e.g., taxi), where 1 = fixed, 2 = movable.</td>
  </tr>
  <tr>
    <td>etime</td>
    <td>integer</td>
    <td>The exposure time in seconds per view that the creative will be displayed before refreshing to the next creative.</td>
  </tr>
  <tr>
    <td>dpi</td>
    <td>integer</td>
    <td>Minimum DPI for text-based creative elements to display clearly.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Publisher <a name="object_publisher"></a>

This object describes the publisher of the media in which ads will be displayed.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string, recommended</td>
    <td>Vendor-specific unique publisher identifier, as used in ads.txt files.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Displayable name of the publisher.</td>
  </tr>
  <tr>
    <td>domain</td>
    <td>string</td>
    <td>Highest level domain of the publisher (e.g., "publisher.com").</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories that describe the publisher using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer</td>
    <td>The taxonomy in use for the "cat" attribute.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Content <a name="object_content"></a>

This object describes the content in which an impression can appear, which may be syndicated or non-syndicated content. This object may be useful when syndicated content contains impressions and does not necessarily match the publisher's general content. An exchange may or may not have knowledge of the page where the content is running as a result of the syndication method (e.g., a video impression embedded in an iframe on an unknown web property or device).

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string</td>
    <td>ID uniquely identifying the content.</td>
  </tr>
  <tr>
    <td>episode</td>
    <td>integer</td>
    <td>Episode number.</td>
  </tr>
  <tr>
    <td>title</td>
    <td>string</td>
    <td>Content title.
Video Examples: "Search Committee" (television), "Star Wars, A New Hope" (movie), or "Endgame" (made for web).
Non-Video Example:  "Why an Antarctic Glacier Is Melting So Quickly" (Time magazine article).</td>
  </tr>
  <tr>
    <td>series</td>
    <td>string</td>
    <td>Content series.
Video Examples: "The Office" (television), "Star Wars" (movie), or "Arby 'N' The Chief" (made for web).
Non-Video Example:  "Ecocentric" (Time Magazine blog).</td>
  </tr>
  <tr>
    <td>season</td>
    <td>string</td>
    <td>Content season (e.g., "Season 3").</td>
  </tr>
  <tr>
    <td>artist</td>
    <td>string</td>
    <td>Artist credited with the content.</td>
  </tr>
  <tr>
    <td>genre</td>
    <td>string</td>
    <td>Genre that best describes the content (e.g., rock, pop, etc).</td>
  </tr>
  <tr>
    <td>album</td>
    <td>string</td>
    <td>Album to which the content belongs; typically for audio.</td>
  </tr>
  <tr>
    <td>isrc</td>
    <td>string</td>
    <td>International Standard Recording Code conforming to ISO-3901.</td>
  </tr>
  <tr>
    <td>url</td>
    <td>string</td>
    <td>URL of the content, for buy-side contextualization or review.</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories describing the content using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer</td>
    <td>The taxonomy in use for the "cat" attribute.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>prodq</td>
    <td>integer</td>
    <td>Production quality.  Refer to List:  Production Qualities.</td>
  </tr>
  <tr>
    <td>context</td>
    <td>integer</td>
    <td>Type of content (game, video, text, etc.).  Refer to List:  Content Contexts.</td>
  </tr>
  <tr>
    <td>rating</td>
    <td>string</td>
    <td>Content rating (e.g., MPAA).</td>
  </tr>
  <tr>
    <td>urating</td>
    <td>string</td>
    <td>User rating of the content (e.g., number of stars, likes, etc.).</td>
  </tr>
  <tr>
    <td>mrating</td>
    <td>integer</td>
    <td>Media rating per IQG guidelines.  Refer to List:  Media Ratings.</td>
  </tr>
  <tr>
    <td>keywords</td>
    <td>string</td>
    <td>Comma separated list of keywords describing the content.</td>
  </tr>
  <tr>
    <td>live</td>
    <td>integer</td>
    <td>Indication of live content, where 0 = not live, 1 = live (e.g., stream, live blog).</td>
  </tr>
  <tr>
    <td>srcrel</td>
    <td>integer</td>
    <td>Source relationship, where 0 = indirect, 1 = direct.</td>
  </tr>
  <tr>
    <td>len</td>
    <td>integer</td>
    <td>Length of content in seconds; typically for video or audio.</td>
  </tr>
  <tr>
    <td>lang</td>
    <td>string</td>
    <td>Content language using ISO-639-1-alpha-2.</td>
  </tr>
  <tr>
    <td>embed</td>
    <td>integer</td>
    <td>Indicator of whether or not the content is embedded off-site from the the site or app described in those objects (e.g., an embedded video player), where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>producer</td>
    <td>object</td>
    <td>Details about the content producer.  Refer to Object:  Producer.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>object array</td>
    <td>Additional user data.  Each "Data" object represents a different data source.  Refer to Object:  Data.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Producer <a name="object_producer"></a>

This object defines the producer of the content in which ad will be displayed.  This is particularly useful when the content is syndicated and may be distributed through different publishers and thus when the producer and publisher are not necessarily the same entity.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string, recommended</td>
    <td>Vendor-specific unique producer identifier.  Useful if content is syndicated and may be posted on a site using embed tags.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Displayable name of the producer.</td>
  </tr>
  <tr>
    <td>domain</td>
    <td>string</td>
    <td>Highest level domain of the producer (e.g., "producer.com").</td>
  </tr>
  <tr>
    <td>cat</td>
    <td>string array</td>
    <td>Array of content categories that describe the producer using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer</td>
    <td>The taxonomy in use for the  "cat" attribute.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  User <a name="object_user"></a>

This object contains information known or derived about the human user of the device (i.e., the audience for advertising).  The user ID is a vendor-specific artifact and may be subject to rotation or other privacy policies.  However, this user ID must be stable long enough to serve reasonably as the basis for frequency capping and retargeting.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string; recommended</td>
    <td>Vendor-specific ID for the user.  At least one of "id" or "buyeruid" is strongly recommended.</td>
  </tr>
  <tr>
    <td>buyeruid</td>
    <td>string; recommended</td>
    <td>Buyer-specific ID for the user as mapped by an exchange for the buyer.  At least one of "id" or "buyeruid" is strongly recommended.</td>
  </tr>
  <tr>
    <td>yob</td>
    <td>integer</td>
    <td>Year of birth as a 4-digit integer.</td>
  </tr>
  <tr>
    <td>gender</td>
    <td>string</td>
    <td>Gender, where "M" = male, "F" = female, "O" = known to be other (i.e., omitted is unknown).</td>
  </tr>
  <tr>
    <td>keywords</td>
    <td>string</td>
    <td>Comma separated list of keywords, interests, or intent.</td>
  </tr>
  <tr>
    <td>consent</td>
    <td>string</td>
    <td>GDPR consent string if applicable, complying with the comply with the IAB standard [Consent String Format](https://bit.ly/2HzD6Kg) in the [Transparency and Consent Framework](https://iabtechlab.com/gdpr-tech) technical specifications.</td>
  </tr>
  <tr>
    <td>geo</td>
    <td>object</td>
    <td>Location of the user's home base (i.e., not necessarily their current location).  Refer to Object:  Geo.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>object array</td>
    <td>Additional user data.  Each "Data" object represents a different data source.  Refer to Object:  Data.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Device <a name="object_device"></a>

This object provides information pertaining to the device through which the user is interacting.  Device information includes its hardware, platform, location, and carrier data.  The device can refer to a mobile handset, a desktop computer, set top box, or other digital device.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer</td>
    <td>The general type of device.  Refer to List:  Device Types.</td>
  </tr>
  <tr>
    <td>ua</td>
    <td>string</td>
    <td>Browser user agent string.</td>
  </tr>
  <tr>
    <td>ifa</td>
    <td>string</td>
    <td>ID sanctioned for advertiser use in the clear (i.e., not hashed).</td>
  </tr>
  <tr>
    <td>dnt</td>
    <td>integer</td>
    <td>Standard "Do Not Track" flag as set in the header by the browser, where 0 = tracking is unrestricted, 1 = do not track.</td>
  </tr>
  <tr>
    <td>lmt</td>
    <td>integer</td>
    <td>"Limit Ad Tracking" signal commercially endorsed (e.g., iOS, Android), where 0 = tracking is unrestricted, 1 = tracking must be limited per commercial guidelines.</td>
  </tr>
  <tr>
    <td>make</td>
    <td>string</td>
    <td>Device make (e.g., "Apple").</td>
  </tr>
  <tr>
    <td>model</td>
    <td>string</td>
    <td>Device model (e.g., "iPhone10,1" when the specific device model is known, "iPhone" otherwise).  The value obtained from the device O/S should be used when available.</td>
  </tr>
  <tr>
    <td>os</td>
    <td>integer</td>
    <td>Device operating system.  Refer to List:  Operating Systems.</td>
  </tr>
  <tr>
    <td>osv</td>
    <td>string</td>
    <td>Device operating system version (e.g., "3.1.2").</td>
  </tr>
  <tr>
    <td>hwv</td>
    <td>string</td>
    <td>Hardware version of the device (e.g., "5S" for iPhone 5S).</td>
  </tr>
  <tr>
    <td>h</td>
    <td>integer</td>
    <td>Physical height of the screen in pixels.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>integer</td>
    <td>Physical width of the screen in pixels.</td>
  </tr>
  <tr>
    <td>ppi</td>
    <td>integer</td>
    <td>Screen size as pixels per linear inch.</td>
  </tr>
  <tr>
    <td>pxratio</td>
    <td>float</td>
    <td>The ratio of physical pixels to device independent pixels.</td>
  </tr>
  <tr>
    <td>js</td>
    <td>integer</td>
    <td>Support for JavaScript, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>lang</td>
    <td>string</td>
    <td>Browser language using ISO-639-1-alpha-2.</td>
  </tr>
  <tr>
    <td>ip</td>
    <td>string</td>
    <td>IPv4 address closest to device.</td>
  </tr>
  <tr>
    <td>ipv6</td>
    <td>string</td>
    <td>IP address closest to device as IPv6.</td>
  </tr>
  <tr>
    <td>xff</td>
    <td>string</td>
    <td>The value of the `x-forwarded-for` header.</td>
  </tr>
  <tr>
    <td>iptr</td>
    <td>integer</td>
    <td>Indicator of truncation of any of the IP attributes (i.e., "ip", "ipv6", "xff"), where 0 = no, 1 = yes (e.g., from 1.2.3.4 to 1.2.3.0).
Refer to tools.ietf.org/html/rfc6235#section-4.1.1 for more information on IP truncation.</td>
  </tr>
  <tr>
    <td>carrier</td>
    <td>string</td>
    <td>Carrier or ISP (e.g., "VERIZON") using exchange curated string names which should be published to bidders a priori.</td>
  </tr>
  <tr>
    <td>mccmnc</td>
    <td>string</td>
    <td>Mobile carrier as the concatenated MCC-MNC code (e.g., "310-005" identifies Verizon Wireless CDMA in the USA).  Refer to en.wikipedia.org/wiki/Mobile_country_code for further information and references.  Note that the dash between the MCC and MNC parts is required to remove parsing ambiguity.</td>
  </tr>
  <tr>
    <td>mccmncsim</td>
    <td>string</td>
    <td>MCC and MNC of the SIM card using the same format as "mccmnc".  When both values are available, a difference between them reveals that a user is roaming.</td>
  </tr>
  <tr>
    <td>contype</td>
    <td>integer</td>
    <td>Network connection type.  Refer to List:  Connection Types.</td>
  </tr>
  <tr>
    <td>geofetch</td>
    <td>integer</td>
    <td>Indicates if the geolocation API will be available to JavaScript code running in display ad, where 0 = no, 1 = yes.</td>
  </tr>
  <tr>
    <td>geo</td>
    <td>object</td>
    <td>Location of the device (i.e., typically the user's current location).  Refer to Object:  Geo.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Geo <a name="object_geo"></a>

This object encapsulates various methods for specifying a geographic location. When subordinate to a "`Device`" object, it indicates the location of the device which can also be interpreted as the user's current location. When subordinate to a "`User`" object, it indicates the location of the user's home base (i.e., not necessarily their current location).

The "`lat`" and "`lon`" attributes should only be passed if they conform to the accuracy depicted in the "`type`" attribute. For example, the centroid of a large region (e.g., postal code) should not be passed.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>type</td>
    <td>integer</td>
    <td>Source of location data; recommended when passing lat/lon.  Refer to List:  Location Types.</td>
  </tr>
  <tr>
    <td>lat</td>
    <td>float</td>
    <td>Latitude from -90.0 to +90.0, where negative is south.</td>
  </tr>
  <tr>
    <td>lon</td>
    <td>float</td>
    <td>Longitude from -180.0 to +180.0, where negative is west.</td>
  </tr>
  <tr>
    <td>accur</td>
    <td>integer</td>
    <td>Estimated location accuracy in meters; recommended when lat/lon are specified and derived from a device's location services (i.e., type = 1).  Note that this is the accuracy as reported from the device.  Consult OS specific documentation (e.g., Android, iOS) for exact interpretation.</td>
  </tr>
  <tr>
    <td>lastfix</td>
    <td>integer</td>
    <td>Number of seconds since this geolocation fix was established.  Note that devices may cache location data across multiple fetches.  Ideally, this value should be from the time the actual fix was taken.</td>
  </tr>
  <tr>
    <td>ipserv</td>
    <td>integer</td>
    <td>Service or provider used to determine geolocation from IP address if applicable (i.e., "type" = 2).  Refer to List:  IP Location Services.</td>
  </tr>
  <tr>
    <td>country</td>
    <td>string</td>
    <td>Country code using ISO-3166-1-alpha-2.
Note that alpha-3 codes may be encountered and vendors are encouraged to be tolerant of them.</td>
  </tr>
  <tr>
    <td>region</td>
    <td>string</td>
    <td>Region code using ISO-3166-2; 2-letter state code if USA.</td>
  </tr>
  <tr>
    <td>metro</td>
    <td>string</td>
    <td>Regional marketing areas such as Nielsen's DMA codes or other similar taxonomy to be agreed among vendors prior to use.
Note that DMA is a trademarked asset of The Nielsen Company.  Vendors are encouraged to ensure their use of DMAs is properly licensed.</td>
  </tr>
  <tr>
    <td>city</td>
    <td>string</td>
    <td>City using United Nations Code for Trade & Transport Locations "UN/LOCODE" with the space between country and city suppressed (e.g., Boston MA, USA = "USBOS").  Refer to [UN/LOCODE Code List](https://www.unece.org/cefact/locode/service/location).</td>
  </tr>
  <tr>
    <td>zip</td>
    <td>string</td>
    <td>ZIP or postal code.</td>
  </tr>
  <tr>
    <td>utcoffset</td>
    <td>integer</td>
    <td>Local time as the number +/- of minutes from UTC.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Data <a name="object_data"></a>

The data and segment objects together allow additional data about the related object (e.g., user, content) to be specified.  This data may be from multiple sources whether from the exchange itself or third parties as specified by the "id" attribute.  When in use, vendor-specific IDs should be communicated *a priori* among the parties.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string</td>
    <td>Vendor-specific ID for the data provider.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Vendor-specific displayable name for the data provider.</td>
  </tr>
  <tr>
    <td>segment</td>
    <td>object array</td>
    <td>Array of "Segment" objects that contain the actual data values.  Refer to Object:  Segment.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Segment <a name="object_segment"></a>

Segment objects are essentially key-value pairs that convey specific units of data.  The parent "`Data`" object is a collection of such values from a given data provider.  When in use, vendor-specific IDs should be communicated *a priori* among the parties.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>id</td>
    <td>string</td>
    <td>ID of the data segment specific to the data provider.</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Displayable name of the data segment specific to the data provider.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>string</td>
    <td>String representation of the data segment value.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Regs <a name="object_regs"></a>

This object contains any known legal, governmental, or industry regulations that are in effect.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>coppa</td>
    <td>integer</td>
    <td>Flag indicating if COPPA regulations apply, where 0 = no, 1 = yes.
The Children's Online Privacy Protection Act (COPPA) was established by the U.S. Federal Trade Commission.</td>
  </tr>
  <tr>
    <td>gdpr</td>
    <td>integer</td>
    <td>Flag indicating if GDPR regulations apply, where 0 = no, 1 = yes.
The General Data Protection Regulation (GDPR) is a regulation of the European Union.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


### Object:  Restrictions <a name="object_restrictions"></a>

This object allows lists of restrictions on ad responses to be specified including specific content categories, advertisers, ads pertaining to specific apps, or creative attributes.

<table>
  <tr>
    <td>Attribute</td>
    <td>Type</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>bcat</td>
    <td>string array</td>
    <td>Block list of content categories using IDs from the taxonomy indicated in "cattax".</td>
  </tr>
  <tr>
    <td>cattax</td>
    <td>integer; default 2</td>
    <td>The taxonomy in use for the "bcat" attribute.  Refer to List:  Category Taxonomies.</td>
  </tr>
  <tr>
    <td>badv</td>
    <td>string array</td>
    <td>Block list of advertisers by their domains (e.g., "ford.com").</td>
  </tr>
  <tr>
    <td>bapp</td>
    <td>string array</td>
    <td>Block list of apps for which ads are disallowed.  These should be bundle or package names (e.g., "com.foo.mygame") and should NOT be app store IDs (e.g., not iTunes store IDs).</td>
  </tr>
  <tr>
    <td>battr</td>
    <td>integer array</td>
    <td>Block list of creative attributes.  Refer to List:  Creative Attributes.</td>
  </tr>
  <tr>
    <td>ext</td>
    <td>object</td>
    <td>Optional vendor-specific extensions.</td>
  </tr>
</table>


## Enumerations <a name="enumerations"></a>

The following lists define enumerations referenced by attributes in AdCOM objects.

### List:  API Frameworks <a name="list_apiframeworks"></a>

The following table is a list of API frameworks either supported by a placement or required by an ad.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>VPAID 1.0</td>
  </tr>
  <tr>
    <td>2</td>
    <td>VPAID 2.0</td>
  </tr>
  <tr>
    <td>3</td>
    <td>MRAID 1.0</td>
  </tr>
  <tr>
    <td>4</td>
    <td>ORMMA</td>
  </tr>
  <tr>
    <td>5</td>
    <td>MRAID 2.0</td>
  </tr>
  <tr>
    <td>6</td>
    <td>MRAID 3.0</td>
  </tr>
  <tr>
    <td>7</td>
    <td>OMID 1.0</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Audit Status Codes <a name="list_auditstatuscodes"></a>

The following table lists the codes used in "`Audit`" objects to reflect status or workflow state.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Pending Audit:  An audit has not yet been completed on this ad.  A recommendation cannot be made to use this ad, but vendors' policies may override.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Pre-Approved:  An audit has not yet been completed on this ad.  Subject to vendors' policies, it can be recommended for use.  However, once the audit has been completed, its status will change and it may or may not be approved for continued use.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Approved:  The audit is complete and the ad is approved for use.  Note, however, that some attributes (e.g., "adomain", "cat", "attr", etc.) may have been changed in the process by the auditor.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Denied:  The audit is complete, but the ad has been found unacceptable in some material aspect and is disapproved for use.</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Changed; Resubmission Requested:  A version of the ad has been detected in use that is materially different from the version that was previously audited, which may result in rejection during use until the ad is resubmitted for audit and approved.  Vendors need to communicate offline as to the criteria that constitutes a material change.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Expired: The ad has been marked as expired by the vendor.  Vendors need to communicate offline as to the expected bidding behavior for ads with this status.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Category Taxonomies <a name="list_categorytaxonomies"></a>


This list identifies the taxonomy in effect when content categories are listed.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>IAB Content Category Taxonomy 1.0.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>IAB Content Category Taxonomy 2.0:  www.iab.com/guidelines/taxonomy</td>
  </tr>
  <tr>
    <td>3</td>
    <td>IAB Ad Product Taxonomy 1.0.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Click Types <a name="list_clicktypes"></a>

The following table lists the types of creative activation (i.e., click) behavior types.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>0</td>
    <td>Non-Clickable</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Clickable - Details Unknown</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Clickable - Embedded Browser/Webview</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Clickable - Native Browser</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Companion Types <a name="list_companiontypes"></a>

The following table lists the options to indicate markup types allowed for companion ads that apply to video and audio ads.  This table is derived from VAST 2.0+ and DAAST 1.0+ specifications.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Static Resource</td>
  </tr>
  <tr>
    <td>2</td>
    <td>HTML Resource</td>
  </tr>
  <tr>
    <td>3</td>
    <td>iframe Resource</td>
  </tr>
</table>


### List:  Connection Types <a name="list_connectiontypes"></a>

The following table lists the options for the type of device connectivity.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Ethernet; Wired Connection</td>
  </tr>
  <tr>
    <td>2</td>
    <td>WIFI</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Cellular Network - Unknown Generation</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Cellular Network - 2G</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Cellular Network - 3G</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Cellular Network - 4G</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Cellular Network - 5G</td>
  </tr>
</table>


### List:  Content Contexts <a name="list_contentcontexts"></a>

The following table lists the various options for indicating the type of content being used or consumed by the user in which ads may appear.  This table has values derived from the TAG Inventory Quality Guidelines (IQG).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Video (i.e., video file or stream such as Internet TV broadcasts)</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Game (i.e., an interactive software game)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Music (i.e., audio file or stream such as Internet radio broadcasts)</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Application (i.e., an interactive software application)</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Text (i.e., primarily textual document such as a web page, eBook, or news article)</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Other (i.e., none of the other categories applies)</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Unknown</td>
  </tr>
</table>


### List:  Creative Attributes <a name="list_creativeattributes"></a>

The following table specifies a standard list of creative attributes that can describe an actual ad or restrictions relative to a given placement.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Audio Ad (Autoplay)</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Audio Ad (User Initiated)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Expandable (Automatic)</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Expandable (User Initiated - Click)</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Expandable (User Initiated - Rollover)</td>
  </tr>
  <tr>
    <td>6</td>
    <td>In-Banner Video Ad (Autoplay)</td>
  </tr>
  <tr>
    <td>7</td>
    <td>In-Banner Video Ad (User Initiated)</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Pop (e.g., Over, Under, or Upon Exit)</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Provocative or Suggestive Imagery</td>
  </tr>
  <tr>
    <td>10</td>
    <td>Shaky, Flashing, Flickering, Extreme Animation, Smileys</td>
  </tr>
  <tr>
    <td>11</td>
    <td>Surveys</td>
  </tr>
  <tr>
    <td>12</td>
    <td>Text Only</td>
  </tr>
  <tr>
    <td>13</td>
    <td>User Interactive (e.g., Embedded Games)</td>
  </tr>
  <tr>
    <td>14</td>
    <td>Windows Dialog or Alert Style</td>
  </tr>
  <tr>
    <td>15</td>
    <td>Has Audio On/Off Button</td>
  </tr>
  <tr>
    <td>16</td>
    <td>Ad Provides Skip Button (e.g. VPAID-rendered skip button on pre-roll video)</td>
  </tr>
  <tr>
    <td>17</td>
    <td>Adobe Flash</td>
  </tr>
  <tr>
    <td>18</td>
    <td>Responsive; Sizeless; Fluid (i.e., creatives that dynamically resize to environment)</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Creative Subtypes - Audio/Video <a name="list_creativesubtypesaudiovideo"></a>

The following table lists the various subtypes of audio and video ad creatives.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>VAST 1.0</td>
  </tr>
  <tr>
    <td>2</td>
    <td>VAST 2.0</td>
  </tr>
  <tr>
    <td>3</td>
    <td>VAST 3.0</td>
  </tr>
  <tr>
    <td>4</td>
    <td>VAST 1.0 Wrapper</td>
  </tr>
  <tr>
    <td>5</td>
    <td>VAST 2.0 Wrapper</td>
  </tr>
  <tr>
    <td>6</td>
    <td>VAST 3.0 Wrapper</td>
  </tr>
  <tr>
    <td>7</td>
    <td>VAST 4.0</td>
  </tr>
  <tr>
    <td>8</td>
    <td>VAST 4.0 Wrapper</td>
  </tr>
  <tr>
    <td>9</td>
    <td>DAAST 1.0</td>
  </tr>
  <tr>
    <td>10</td>
    <td>DAAST 1.0 Wrapper</td>
  </tr>
  <tr>
    <td>11</td>
    <td>VAST 4.1</td>
  </tr>
  <tr>
    <td>12</td>
    <td>VAST 4.1 Wrapper</td>
  </tr>
</table>


### List:  Creative Subtypes - Display <a name="list_creativesubtypesdisplay"></a>

The following table lists the various subtypes of display ad creatives.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>HTML</td>
  </tr>
  <tr>
    <td>2</td>
    <td>AMPHTML</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Structured Image Object</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Structured Native Object</td>
  </tr>
</table>


### List:  Delivery Methods <a name="list_deliverymethods"></a>

The following table lists the various options for the delivery of video or audio content.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Streaming</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Progressive</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Download</td>
  </tr>
</table>


### List:  Device Types <a name="list_devicetypes"></a>

The following table lists the types of devices.  This table has values derived from the TAG Inventory Quality Guidelines (IQG).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Mobile/Tablet - General</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Personal Computer</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Connected TV</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Phone</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Tablet</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Connected Device</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Set Top Box</td>
  </tr>
</table>


### List:  Display Context Types <a name="list_displaycontexttypes"></a>

The following table lists the types of context in which a native ad may appear (i.e., the type of content surrounding the ad on the page).  This is intended to denote primary content although other content may also appear on the page.  Note that there are two levels of detail grouped by 10s (i.e., 12 is a refined case of 100).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>10</td>
    <td>Content-centric context (e.g., newsfeed, article, image gallery, video gallery, etc.).</td>
  </tr>
  <tr>
    <td>11</td>
    <td>Primarily article content, which could include images, etc. as part of the article.</td>
  </tr>
  <tr>
    <td>12</td>
    <td>Primarily video content.</td>
  </tr>
  <tr>
    <td>13</td>
    <td>Primarily audio content.</td>
  </tr>
  <tr>
    <td>14</td>
    <td>Primarily image content.</td>
  </tr>
  <tr>
    <td>15</td>
    <td>User-generated content (e.g., forums, comments, etc.).</td>
  </tr>
  <tr>
    <td>20</td>
    <td>Social-centric context (e.g., social network feed, email, chat, etc.).</td>
  </tr>
  <tr>
    <td>21</td>
    <td>Primarily email content.</td>
  </tr>
  <tr>
    <td>22</td>
    <td>Primarily chat/IM content.</td>
  </tr>
  <tr>
    <td>30</td>
    <td>Product context (e.g., product listings, details, recommendations, reviews, etc.).</td>
  </tr>
  <tr>
    <td>31</td>
    <td>App store/marketplace.</td>
  </tr>
  <tr>
    <td>32</td>
    <td>Product reviews site primarily, which may sell product secondarily.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Display Placement Types <a name="list_displayplacementtypes"></a>

The following table lists the general types of display placements; the locations where a native ad may be shown in relationship to the surrounding content.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>In the feed of content (e.g., as an item inside the organic feed, grid, listing, carousel, etc.).</td>
  </tr>
  <tr>
    <td>2</td>
    <td>In the atomic unit of the content (e.g., in the article page or single image page).</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Outside the core content (e.g., in the ads section on the right rail, as a banner-style placement near the content, etc.).</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Recommendation widget; most commonly presented below article content.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  DOOH Venue Types <a name="list_doohvenuetypes"></a>

This list presents the digital out-of-home venue types and is derived from [DPAA Programmatic Standards](https://dp-aa.org/dpaa-programmatic-standards/).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Airborne</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Airports - General</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Airports - Baggage Claim</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Airports - Terminal</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Airports - Lounges</td>
  </tr>
  <tr>
    <td>6</td>
    <td>ATMs</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Backlights</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Bars</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Benches</td>
  </tr>
  <tr>
    <td>10</td>
    <td>Bike Racks</td>
  </tr>
  <tr>
    <td>11</td>
    <td>Bulletins</td>
  </tr>
  <tr>
    <td>12</td>
    <td>Buses</td>
  </tr>
  <tr>
    <td>13</td>
    <td>Cafes</td>
  </tr>
  <tr>
    <td>14</td>
    <td>Casual Dining Restaurants</td>
  </tr>
  <tr>
    <td>15</td>
    <td>Child Care</td>
  </tr>
  <tr>
    <td>16</td>
    <td>Cinema</td>
  </tr>
  <tr>
    <td>17</td>
    <td>City Information Panels</td>
  </tr>
  <tr>
    <td>18</td>
    <td>Convenience Stores</td>
  </tr>
  <tr>
    <td>19</td>
    <td>Dedicated Wild Posting</td>
  </tr>
  <tr>
    <td>20</td>
    <td>Doctors Offices - General</td>
  </tr>
  <tr>
    <td>21</td>
    <td>Doctors Offices - Obstetrics</td>
  </tr>
  <tr>
    <td>22</td>
    <td>Doctors Offices - Pediatrics</td>
  </tr>
  <tr>
    <td>23</td>
    <td>Family entertainment</td>
  </tr>
  <tr>
    <td>24</td>
    <td>Ferries</td>
  </tr>
  <tr>
    <td>25</td>
    <td>Financial Services</td>
  </tr>
  <tr>
    <td>26</td>
    <td>Gas Stations</td>
  </tr>
  <tr>
    <td>27</td>
    <td>Golf Courses</td>
  </tr>
  <tr>
    <td>28</td>
    <td>Gyms</td>
  </tr>
  <tr>
    <td>29</td>
    <td>Hospitals</td>
  </tr>
  <tr>
    <td>30</td>
    <td>Hotels</td>
  </tr>
  <tr>
    <td>31</td>
    <td>Junior Posters</td>
  </tr>
  <tr>
    <td>32</td>
    <td>Kiosks</td>
  </tr>
  <tr>
    <td>33</td>
    <td>Malls - General</td>
  </tr>
  <tr>
    <td>34</td>
    <td>Malls - Food Courts</td>
  </tr>
  <tr>
    <td>35</td>
    <td>Marine</td>
  </tr>
  <tr>
    <td>36</td>
    <td>Mobile Billboards</td>
  </tr>
  <tr>
    <td>37</td>
    <td>Movie Theater Lobbies</td>
  </tr>
  <tr>
    <td>38</td>
    <td>Newsstands</td>
  </tr>
  <tr>
    <td>39</td>
    <td>Office Buildings</td>
  </tr>
  <tr>
    <td>40</td>
    <td>Phone Kiosks</td>
  </tr>
  <tr>
    <td>41</td>
    <td>Posters</td>
  </tr>
  <tr>
    <td>42</td>
    <td>QSR</td>
  </tr>
  <tr>
    <td>43</td>
    <td>Rail</td>
  </tr>
  <tr>
    <td>44</td>
    <td>Receptacles</td>
  </tr>
  <tr>
    <td>45</td>
    <td>Resorts / Leisure</td>
  </tr>
  <tr>
    <td>46</td>
    <td>Retail</td>
  </tr>
  <tr>
    <td>47</td>
    <td>Salons</td>
  </tr>
  <tr>
    <td>48</td>
    <td>Shelters</td>
  </tr>
  <tr>
    <td>49</td>
    <td>Sports Arenas</td>
  </tr>
  <tr>
    <td>50</td>
    <td>Subway</td>
  </tr>
  <tr>
    <td>51</td>
    <td>Taxis / Wrapped vehicles</td>
  </tr>
  <tr>
    <td>52</td>
    <td>Truckside</td>
  </tr>
  <tr>
    <td>53</td>
    <td>Universities</td>
  </tr>
  <tr>
    <td>54</td>
    <td>Urban Panels</td>
  </tr>
  <tr>
    <td>55</td>
    <td>Veterinarian Offices</td>
  </tr>
  <tr>
    <td>56</td>
    <td>Walls / Spectaculars</td>
  </tr>
  <tr>
    <td>57</td>
    <td>Other</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Event Tracking Methods <a name="list_eventtrackingmethods"></a>

The following table lists the available methods of tracking of ad events.  Vendor specific codes may include custom measurement companies (e.g., Moat, Doubleverify, IAS, etc.).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Image-Pixel:  URL provided will be inserted as a 1x1 pixel at the time of the event.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>JavaScript:  URL provided will be inserted as a JavaScript tag at the time of the event.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Event Types <a name="list_eventtypes"></a>

The following table lists the types of ad events available for tracking.  These types refer to the actual event, timing, etc.; not the method of firing.  Scripts that are performing measurement should be deployed at impression time.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>loaded:  Creative pre-cached or pre-loaded; prior to initial rendering.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>impression:  Initial creative rending.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>viewable-mrc50:  Visible impression using MRC definition of 50% in view for 1 second.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>viewable-mrc100:  100% in view for 1 second (i.e., the GroupM standard).</td>
  </tr>
  <tr>
    <td>5</td>
    <td>viewable-video50:  Visible impression for video using MRC definition of 50% in view for 2 seconds.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Expandable Directions <a name="list_expandabledirections"></a>

The following table lists the directions in which an expandable ad may expand, given the positioning of the ad unit on the page and constraints imposed by the content.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Left</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Right</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Up</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Down</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Full Screen</td>
  </tr>
</table>


### List:  Feed Types <a name="list_feedtypes"></a>

The following table lists the types of feeds, typically for audio.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Music Service</td>
  </tr>
  <tr>
    <td>2</td>
    <td>FM/AM Broadcast</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Podcast</td>
  </tr>
</table>


### List:  IP Location Services <a name="list_iplocationservices"></a>

The following table lists the services and/or vendors used for resolving IP addresses to geolocations.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>ip2location</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Neustar (Quova)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>MaxMind</td>
  </tr>
  <tr>
    <td>4</td>
    <td>NetAcuity (Digital Element)</td>
  </tr>
</table>


### List:  Linearity Modes <a name="list_linearitymodes"></a>

The following table indicates the options for media linearity, typically for video.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Linear (i.e., In-Stream such as Pre-Roll, Mid-Roll, Post-Roll)</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Non-Linear (i.e., Overlay)</td>
  </tr>
</table>


### List:  Location Types <a name="list_locationtypes"></a>

The following table lists the options to indicate how the geographic information was determined.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>GPS/Location Services</td>
  </tr>
  <tr>
    <td>2</td>
    <td>IP Address</td>
  </tr>
  <tr>
    <td>3</td>
    <td>User Provided (e.g., registration data)</td>
  </tr>
</table>


### List:  Media Ratings <a name="list_mediaratings"></a>

The following table lists the media ratings used in describing content based on the TAG Inventory Quality Guidelines (IQG) v2.1 categorization. Refer to [www.iab.com/guidelines/digital-video-suite](https://www.iab.com/guidelines/digital-video-suite) for more information.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>All Audiences</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Everyone Over Age 12</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Mature Audiences</td>
  </tr>
</table>


### List:  Native Data Asset Types <a name="list_nativedataassettypes"></a>

The following table is a list of common data asset types.  This list is non-exhaustive and is intended to be expanded over time.  Size recommendations are noted as "*maximum length of at least*", which means the publisher or supply platform should support a maximum length of at least this value and the buying platform knows that a string of this size should be accepted.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>sponsored:  "Sponsored By" message which should contain the brand name of the sponsor.  Recommended maximum length of at least 25 characters.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>desc:  Descriptive text associated with the product or service being advertised.  Long text lengths may be truncated or ellipsed when rendered.  Recommended maximum length of at least 140 characters.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>rating:  Numeric rating of the product (e.g., an app's rating).  Recommended integer range of 0-5.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>likes:  Number of social ratings or "likes" of the product.</td>
  </tr>
  <tr>
    <td>5</td>
    <td>downloads:  Number downloads and/or installs of the product.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>price:  Price of the product, app, or in-app purchase.  Value  should include currency symbol in localized format (e.g., "$10").</td>
  </tr>
  <tr>
    <td>7</td>
    <td>saleprice:  Sale price that can be used together with "price" to indicate a comparative discounted price.  Value should include currency symbol in localized format (e.g., "$8.50").</td>
  </tr>
  <tr>
    <td>8</td>
    <td>phone:  A formatted phone number.</td>
  </tr>
  <tr>
    <td>9</td>
    <td>address:  A formatted address.</td>
  </tr>
  <tr>
    <td>10</td>
    <td>desc2:  Additional descriptive text associated with the product.</td>
  </tr>
  <tr>
    <td>11</td>
    <td>displayurl:  Display URL for the ad.  To be used when sponsoring entity doesn't own the content (e.g., "Sponsored by Brand on Site", where Site is specified in this data asset).</td>
  </tr>
  <tr>
    <td>12</td>
    <td>ctatext:  Description of the call to action (CTA) button for the destination URL.  Recommended maximum length of at least 15 characters.</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Native Image Asset Types <a name="list_nativeimageassettypes"></a>

The following table is a list of common image asset types.  This list is non-exhaustive and is intended to be expanded over time.  Size recommendations are noted as "*maximum height or width of at least*", which means the publisher or supply platform should support a maximum height or width of at least this value and the buying platform knows that an image of this size should be accepted.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Icon:  Icon image.
Maximum height at least 50 device independent pixels (DIPS); aspect ratio 1:1.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Main:  Large image preview for the ad.
At least one of 2 size variants required:
Small:  Maximum height at least 627 DIPS; maximum width at least 627, 836, or 1198 DIPS (i.e., aspect ratios of 1:1, 4:3, or 1.91:1, respectively).
Large: Maximum height at least 200 DIPS; maximum width at least 200, 267, or 382 DIPS (i.e., aspect ratios of 1:1, 4:3, or 1.91:1, respectively).</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Operating Systems <a name="list_operatingsystems"></a>

The following table lists the options for device operating system.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>0</td>
    <td>Other Not Listed</td>
  </tr>
  <tr>
    <td>1</td>
    <td>3DS System Software</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Android</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Apple TV Software</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Asha</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Bada</td>
  </tr>
  <tr>
    <td>6</td>
    <td>BlackBerry</td>
  </tr>
  <tr>
    <td>7</td>
    <td>BREW</td>
  </tr>
  <tr>
    <td>8</td>
    <td>ChromeOS</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Darwin</td>
  </tr>
  <tr>
    <td>10</td>
    <td>FireOS</td>
  </tr>
  <tr>
    <td>11</td>
    <td>FirefoxOS</td>
  </tr>
  <tr>
    <td>12</td>
    <td>HelenOS</td>
  </tr>
  <tr>
    <td>13</td>
    <td>iOS</td>
  </tr>
  <tr>
    <td>14</td>
    <td>Linux</td>
  </tr>
  <tr>
    <td>15</td>
    <td>MacOS</td>
  </tr>
  <tr>
    <td>16</td>
    <td>MeeGo</td>
  </tr>
  <tr>
    <td>17</td>
    <td>MorphOS</td>
  </tr>
  <tr>
    <td>18</td>
    <td>NetBSD</td>
  </tr>
  <tr>
    <td>19</td>
    <td>NucleusPLUS</td>
  </tr>
  <tr>
    <td>20</td>
    <td>PS Vita System Software</td>
  </tr>
  <tr>
    <td>21</td>
    <td>PS3 System Software</td>
  </tr>
  <tr>
    <td>22</td>
    <td>PS4 Software</td>
  </tr>
  <tr>
    <td>23</td>
    <td>PSP System Software</td>
  </tr>
  <tr>
    <td>24</td>
    <td>Symbian</td>
  </tr>
  <tr>
    <td>25</td>
    <td>Tizen</td>
  </tr>
  <tr>
    <td>26</td>
    <td>WatchOS</td>
  </tr>
  <tr>
    <td>27</td>
    <td>WebOS</td>
  </tr>
  <tr>
    <td>28</td>
    <td>Windows</td>
  </tr>
  <tr>
    <td>500+</td>
    <td>Vendor-specific codes.</td>
  </tr>
</table>


### List:  Placement Positions <a name="list_placementpositions"></a>

The following table lists the placement positions as a relative measure of visibility or prominence.  This table has values derived from the TAG Inventory Quality Guidelines (IQG).

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Above The Fold</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Locked (i.e., fixed position)</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Below The Fold</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Header</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Footer</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Sidebar</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Fullscreen</td>
  </tr>
</table>


### List:  Placement Subtypes - Video <a name="list_placementsubtypesvideo"></a>

The following table lists the various types of video placements derived largely from the IAB Digital Video Guidelines.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>In-Stream:  Played before, during or after the streaming video content that the consumer has requested (e.g., Pre-roll, Mid-roll, Post-roll).</td>
  </tr>
  <tr>
    <td>2</td>
    <td>In-Banner:  Exists within a web banner that leverages the banner space to deliver a video experience as opposed to another static or rich media format.  The format relies on the existence of display ad inventory on the page for its delivery.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>In-Article:  Loads and plays dynamically between paragraphs of editorial content; existing as a standalone branded message.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>In-Feed:  Found in content, social, or product feeds.</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Interstitial/Slider/Floating:  Covers the entire or a portion of screen area, but is always on screen while displayed (i.e. cannot be scrolled out of view).</td>
  </tr>
</table>


### List:  Playback Cessation Modes <a name="list_playbackcessationmodes"></a>

The following table lists the various modes for when media playback terminates.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>On Video Completion or when Terminated by User</td>
  </tr>
  <tr>
    <td>2</td>
    <td>On Leaving Viewport or when Terminated by User</td>
  </tr>
  <tr>
    <td>3</td>
    <td>On Leaving Viewport Continues as a Floating/Slider Unit until Video Completion or when Terminated by User</td>
  </tr>
</table>


### List:  Playback Methods <a name="list_playbackmethods"></a>

The following table lists the various media playback methods.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Initiates on Page Load with Sound On</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Initiates on Page Load with Sound Off by Default</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Initiates on Click with Sound On</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Initiates on Mouse-Over with Sound On</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Initiates on Entering Viewport with Sound On</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Initiates on Entering Viewport with Sound Off by Default</td>
  </tr>
</table>


### List:  Production Qualities <a name="list_productionqualities"></a>

The following table lists the options for content quality.  These values are defined by the IAB; refer to [www.iab.com/wp-content/uploads/2015/03/long-form-video-final.pdf](www.iab.com/wp-content/uploads/2015/03/long-form-video-final.pdf) for more information.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Professionally Produced</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Prosumer</td>
  </tr>
  <tr>
    <td>3</td>
    <td>User Generated (UGC)</td>
  </tr>
</table>


### List:  Size Units <a name="list_sizeunits"></a>

The following table lists the units of height and width used by creatives, assets, and placement specifications where noted.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Device Independent Pixels (DIPS)</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Inches</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Centimeters</td>
  </tr>
</table>


### List:  Start Delay Modes <a name="list_startdelaymodes"></a>

The following table lists the various options for the video or audio start delay.  If the start delay value is greater than 0, then the position is mid-roll and the value indicates the start delay.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>>0</td>
    <td>Mid-Roll (value indicates start delay in second)</td>
  </tr>
  <tr>
    <td>0</td>
    <td>Pre-Roll</td>
  </tr>
  <tr>
    <td>-1</td>
    <td>Generic Mid-Roll</td>
  </tr>
  <tr>
    <td>-2</td>
    <td>Generic Post-Roll</td>
  </tr>
</table>


### List:  Volume Normalization Modes <a name="list_volumenormalizationmodes"></a>

The following table lists the types of volume normalization modes, typically for audio.

<table>
  <tr>
    <td>Value</td>
    <td>Definition</td>
  </tr>
  <tr>
    <td>0</td>
    <td>None</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Ad Volume Average Normalized to Content</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Ad Volume Peak Normalized to Content</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Ad Loudness Normalized to Content</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Custom Volume Normalization</td>
  </tr>
</table>


# Appendix A:  Additional Resources <a name="appendixa_additionalresources"></a>

Interactive Advertising Bureau Technology Laboratory (IAB Tech Lab)  
[www.iabtechlab.com](https://www.iabtechlab.com)

Creative Commons / Attribution License  
[creativecommons.org/licenses/by/3.0](https://creativecommons.org/licenses/by/3.0)

AdCOM Project on Github  
[https://github.com/InteractiveAdvertisingBureau/AdCOM](https://github.com/InteractiveAdvertisingBureau/AdCOM)

OpenRTB v3.0 Specification  
[https://github.com/InteractiveAdvertisingBureau/openrtb](https://github.com/InteractiveAdvertisingBureau/openrtb)

IAB Resources & TAG Inventory Quality Guidelines (IQG)  
[www.iab.com/guidelines/taxonomy](https://www.iab.com/guidelines/taxonomy)
[www.iab.com/guidelines/digital-video-suite](https://www.iab.com/guidelines/digital-video-suite) 
[www.iab.com/wp-content/uploads/2015/03/long-form-video-final.pdf](https://www.iab.com/wp-content/uploads/2015/03/long-form-video-final.pdf)
[github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework)
[www.tagtoday.net/iqg/guidelines](https://www.tagtoday.net/iqg/guidelines)

Digital Place-Based Advertising Association (DPAA)  
[dp-aa.org](https://dp-aa.org)

United Nations Code for Trade & Transport Locations - UN/LOCODE"  
[www.unece.org/cefact/locode/service/location](https://www.unece.org/cefact/locode/service/location) 

IP Flow Anonymization Support / Truncation, Internet Engineering Task Force (IETF)  
[tools.ietf.org/html/rfc6235#section-4.1.1](https://tools.ietf.org/html/rfc6235#section-4.1.1) 

MCC-MNC Codes for Mobile Carriers, Wikipedia  
[en.wikipedia.org/wiki/Mobile_country_code](https://en.wikipedia.org/wiki/Mobile_country_code) 

JavaScript Object Notation (JSON)  
[www.json.org](http://www.json.org)

Date/Time Format: ISO-8601; W3C Profile  
[www.w3.org/TR/NOTE-datetime](https://www.w3.org/TR/NOTE-datetime)


# Appendix B:  Change Log <a name="appendixb_changelog"></a>

This appendix serves as an index of specification changes from the current version to the previous.  These changes pertain only to the substance of the specification and not routine document formatting, information organization, or content without technical impact.

Since v1.0 is the initial version of AdCOM, the change log is omitted.

# Appendix C:  OpenRTB Interfaces <a name="appendixc_openrtbinterfaces"></a>

As OpenRTB v3.0+ is a very popular transaction layer that uses AdCOM, this appendix is provided to show the interface between the two specifications.  This is presented here as informational only; please refer to the current OpenRTB specification v3.0+ for official details on OpenRTB.

In the JSON snippets that follow, AdCOM objects are shown within OpenRTB payloads.    The ellipses indicate attributes unrelated to this example that have been omitted for brevity.

## Request Context <a name="requestcontext"></a>

The following is an abbreviated example of an OpenRTB v3.x bid request.  It self-identifies as OpenRTB and shows its version as "3.0".  It also shows that it is using AdCOM v1.0 as its domain layer.

The "`context`" object is the OpenRTB interface to AdCOM context objects.  It can contain any of the top-level context objects, all of which are optional, and their subordinates.  This example includes top-level objects "`regs`", "`restrictions`", "`site`" (no more than one distribution channel subtype may be included), "`user`", and "`device`".

This example is indicating a mobile optimized website and some basic details about the site and its publisher.  The user is a female born in 1990.  She is using an Apple iPhone 6S, running iOS 11.4.1, and is connected via the Verizon network.  Her device (and presumably she) is currently located in Boston MA, USA, during eastern standard time.  She is not subject to GDPR or COPPA.  We would also like to block adult, illegal, and uncategorized content as well as ads from car makers Ford and Buick.




```
{
   "openrtb": {
      "ver": "3.0",
      "domainspec": "adcom",
      "domainver": "1.0",
      "request": {
         ...
         "context": {
            "regs": {
               "gdpr": 0,
               "coppa": 0
            },
            "restrictions": {
               "bcat": [ "IAB24", "IAB25", "IAB26" ],
               "cattax": 1,
               "badv": [ "ford.com", "buick.com" ]
            },
            "site": {
               "id": "1234",
               "name": "Awesome Example Site",
               "domain": "examplesitedomain.com",
               "mobile": 1,
               "amp": 0,
               "publisher": {
                  "id": "9876",
                  "name": "Example Publisher, Inc.",
                  "domain": "examplepubdomain.com"
               }
            },
            "user": {
               "id": "a0af45c77890045deec100acb8443baff57c",
               "buyeruid": "fcd4282456238256034abcdef220d9aa5892",
               "yob": 1990,
               "gender": "F"
            },
            "device": {
               "type": 4,
               "ifa": "8846d6fa10008bceaaf322908dfcb221",
               "ip": "1.2.3.4",
               "ua": "...user agent string...",
               "make": "Apple",
               "model": "iPhone",
               "hwv": "6s",
               "os": 13,
               "osv": "11.4.1",
               "mccmnc": "310-005",
               "geo": {
                  "type": 1,
                  "lat": 42.3601,
                  "lon": 71.0581,
                  "country": "USA",
                  "utcoffset": -300
               }
            }
         }
         ...
      }
   }
}
```



## Item Specifications <a name="itemspecs"></a>

The following snippet is an abbreviated OpenRTB v3.x bid request that offers a single item for sale.

The "`spec`" object within an "`item`" is the OpenRTB interface to AdCOM placement objects.  It contains one "`Placement`" top-level object and its subordinates.

This example is indicating a display placement that must be secure.  Either a structured banner or AMPHTML is acceptable and if the latter, the AMP rendering mode will be *early*.  The placement is not interstitial, two possible sizes are offered (i.e., 320x50 and 320x250), and a simple pixel tracker for the impression event is supported.


```
{
   "openrtb": {
      "ver": "3.0",
      "domainspec": "adcom",
      "domainver": "1.0",
      "request": {
         ...
         "item": [
            {
               ...
               "spec": {
                  "placement": {
                     "tagid": "plc-ftr-123abc",
                     "secure": 1,
                     "display": {
                        "ctype": [ 2, 3 ],
                        "ampren": 0,
                        "instl": 0,
                        "displayfmt": [
                           {
                              "w": 320,
                              "h": 50
                           },
                           {
                              "w": 320,
                              "h": 250
                           }
                        ],
                        "event": [
                           {
                              "type": 1,
                              "method": 1
                           }
                        ]
                     }
                  }
               }
               ...
            }
         ]
         ...
      }
   }
}
```



## Media Response <a name="mediaresponse"></a>

The following is an abbreviated example of an OpenRTB v3.x bid response.  It self-identifies as OpenRTB and shows its version as "3.0".  It also shows that it is using AdCOM v1.0 as its domain layer.

The "`media`" object is the OpenRTB interface to AdCOM media objects.  It contains one "`Ad`" top-level object and its subordinates.

This example is indicating a secure display ad for Ford using a structured banner object with a 320x50 JPEG creative.  A pixel tracker for the impression rendering event is requested.


```
{
   "openrtb": {
      "ver": "3.0",
      "domainspec": "adcom",
      "domainver": "1.0",
      "response": {
         ...
         "seatbid": [
            {
               ...
               "bid": [
                  {
                     ...
                     "media": {
                        "ad": {
                           "id": "d0bcb39723af87c2bb00942afee5710e",
                           "adomain": [ "ford.com" ],
                           "cid": "campaign-xyz.123",
                           "secure": 1,
                           "display": {
                              "mime": "image/jpeg",
                              "type": 3,
                              "w": 320,
                              "h": 50,
                              "banner": {
                                 "img": "https://somebuyer.com/creative",
                                 "link": {
                                    "url": "https://somebuyer.com/click",
                                    "urlfb": "https://somebuyer.com"
                                 }
                              },
                              "event": [
                                 {
                                    "type": 1, "method": 1,
                                    "url": "https://somebuyer.com/pixel"
                                 }
                              ]
                           }
                        }
                     }
                     ...
                  }
               ]
            }
         ]
      }
   }
}
```


