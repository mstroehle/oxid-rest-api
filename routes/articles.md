---
description: >-
  Article CRUD. You can interact with the article data directly via database or
  by using full-blown OXID objects (load, save, delete) by adding "/object/" to
  the URLs, e.g. "/rest/v1/object/articles".
---

# Articles

{% api-method method="get" host="https://YOUT\_SHOP\_URL" path="/rest/v1/articles" %}
{% api-method-summary %}
all articles
{% endapi-method-summary %}

{% api-method-description %}
Get all articles.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="filter" type="string" required=false %}
filter\[\]=oxactive\|=\|1&filter\[\]=oxtitle\|like\|kite
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "OXID": "05848170643ab0deb9914566391c0c63",
    "OXSHOPID": 1,
    "OXPARENTID": "",
    "OXACTIVE": 1,
    "OXHIDDEN": 0,
    "OXACTIVEFROM": "0000-00-00 00:00:00",
    "OXACTIVETO": "0000-00-00 00:00:00",
    "OXARTNUM": "1402",
    "OXEAN": "",
    "OXDISTEAN": "",
    "OXMPN": "",
    "OXTITLE": "Trapez ION MADTRIXX",
    "OXSHORTDESC": "Neues Freestyle Trapez mit einer schlank geschnittenen Outline",
    "OXPRICE": 159,
    ...
},
{
    "OXID": "0584e8b766a4de2177f9ed11d1587f55",
    "OXSHOPID": 1,
    "OXPARENTID": "",
    "OXACTIVE": 1,
    "OXHIDDEN": 0,
    "OXACTIVEFROM": "0000-00-00 00:00:00",
    "OXACTIVETO": "0000-00-00 00:00:00",
    "OXARTNUM": "1501",
    "OXEAN": "",
    "OXDISTEAN": "",
    "OXMPN": "",
    "OXTITLE": "Klebeband DACRON KITEFIX",
    "OXSHORTDESC": "Ideal für kleine Reparaturen am Kite",
    "OXPRICE": 7.99,
    ...
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
No artcicles found
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://YOUR\_SHOP\_URL" path="/rest/v1/articles/{id}" %}
{% api-method-summary %}
one article
{% endapi-method-summary %}

{% api-method-description %}
Get one article by id \(oxarticles.oxid\).
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
oxid
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "OXID": "05848170643ab0deb9914566391c0c63",
    "OXSHOPID": 1,
    "OXPARENTID": "",
    "OXACTIVE": 1,
    "OXHIDDEN": 0,
    "OXACTIVEFROM": "0000-00-00 00:00:00",
    "OXACTIVETO": "0000-00-00 00:00:00",
    "OXARTNUM": "1402",
    "OXEAN": "",
    "OXDISTEAN": "",
    "OXMPN": "",
    "OXTITLE": "Trapez ION MADTRIXX",
    "OXSHORTDESC": "Neues Freestyle Trapez mit einer schlank geschnittenen Outline",
    "OXPRICE": 159,
    ...
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
Article with {id} not found
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Use `/rest/v1/object/articles` to get the whole oxid object \(see [Installation](../installation.md#installation-within-oxid)\).
{% endhint %}

{% api-method method="put" host="https://YOUR\_SHOP\_URL" path="/rest/v1/articles/{id}" %}
{% api-method-summary %}
update one article
{% endapi-method-summary %}

{% api-method-description %}
Update one article by id \(oxarticles.oxid\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
oxid
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=false %}
data as JSON
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns the changed article data
{% endapi-method-response-example-description %}

```
{
    "OXID": "04c147a4494fcf5766a4074958ab633b",
    "OXSHOPID": 1,
    "OXPARENTID": "0584e8b766a4de2177f9ed11d1587f55",
    "OXACTIVE": 0,
    "OXHIDDEN": 1,
    "OXACTIVEFROM": "2018-11-10 09:28:59",
    "OXACTIVETO": "2098-11-10 09:28:59",
    "OXARTNUM": "400-01f",
    "OXEAN": "",
    "OXDISTEAN": "",
    "OXMPN": "",
    "OXTITLE": "",
    "OXSHORTDESC": "",
    "OXPRICE": 7.99,
    "OXBLFIXEDPRICE": 0,
    "OXPRICEA": 0,
    "OXPRICEB": 0,
    "OXPRICEC": 0,
    "OXBPRICE": 0,
    "OXTPRICE": 0,
    "OXUNITNAME": "",
    "OXUNITQUANTITY": 0,
    "OXEXTURL": "",
    "OXURLDESC": "",
    "OXURLIMG": "",
    "OXVAT": null,
    "OXTHUMB": "",
    "OXICON": "",
    "OXPIC1": "",
    "OXPIC2": "",
    "OXPIC3": "",
    "OXPIC4": "",
    "OXPIC5": "",
    "OXPIC6": "",
    "OXPIC7": "",
    "OXPIC8": "",
    "OXPIC9": "",
    "OXPIC10": "",
    "OXPIC11": "",
    "OXPIC12": "",
    "OXWEIGHT": 0,
    "OXSTOCK": 6,
    "OXSTOCKFLAG": 1,
    "OXSTOCKTEXT": "",
    "OXNOSTOCKTEXT": "",
    "OXDELIVERY": "2018-11-10",
    "OXINSERT": "2010-12-06 00:00:00",
    "OXTIMESTAMP": "2017-12-21 11:27:11",
    "OXLENGTH": 0,
    "OXWIDTH": 0,
    "OXHEIGHT": 0,
    "OXFILE": "",
    "OXSEARCHKEYS": "",
    "OXTEMPLATE": "",
    "OXQUESTIONEMAIL": "",
    "OXISSEARCH": 0,
    "OXISCONFIGURABLE": 0,
    "OXVARNAME": "",
    "OXVARSTOCK": 0,
    "OXVARCOUNT": 0,
    "OXVARSELECT": "weiß",
    "OXVARMINPRICE": 0,
    "OXVARMAXPRICE": 0,
    "OXVARNAME_1": "",
    "OXVARSELECT_1": "white",
    "OXVARNAME_2": "",
    "OXVARSELECT_2": "",
    "OXVARNAME_3": "",
    "OXVARSELECT_3": "",
    "OXTITLE_1": "",
    "OXSHORTDESC_1": "",
    "OXURLDESC_1": "",
    "OXSEARCHKEYS_1": "",
    "OXTITLE_2": "",
    "OXSHORTDESC_2": "",
    "OXURLDESC_2": "",
    "OXSEARCHKEYS_2": "",
    "OXTITLE_3": "",
    "OXSHORTDESC_3": "",
    "OXURLDESC_3": "",
    "OXSEARCHKEYS_3": "",
    "OXBUNDLEID": "",
    "OXFOLDER": "",
    "OXSUBCLASS": "oxarticle",
    "OXSTOCKTEXT_1": "",
    "OXSTOCKTEXT_2": "",
    "OXSTOCKTEXT_3": "",
    "OXNOSTOCKTEXT_1": "",
    "OXNOSTOCKTEXT_2": "",
    "OXNOSTOCKTEXT_3": "",
    "OXSORT": 0,
    "OXSOLDAMOUNT": 0,
    "OXNONMATERIAL": 0,
    "OXFREESHIPPING": 0,
    "OXREMINDACTIVE": 0,
    "OXREMINDAMOUNT": 0,
    "OXAMITEMID": "",
    "OXAMTASKID": "",
    "OXVENDORID": "",
    "OXMANUFACTURERID": "",
    "OXSKIPDISCOUNTS": 0,
    "OXRATING": 0,
    "OXRATINGCNT": 0,
    "OXMINDELTIME": 1,
    "OXMAXDELTIME": 3,
    "OXDELTIMEUNIT": "WEEK",
    "OXUPDATEPRICE": 0,
    "OXUPDATEPRICEA": 0,
    "OXUPDATEPRICEB": 0,
    "OXUPDATEPRICEC": 0,
    "OXUPDATEPRICETIME": "2018-11-10 09:28:59",
    "OXISDOWNLOADABLE": 0,
    "OXSHOWCUSTOMAGREEMENT": 1
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Use `/rest/v1/object/articles` to update the whole oxid object \(see [Installation](../installation.md#installation-within-oxid)\).
{% endhint %}

{% page-ref page="filters.md" %}

