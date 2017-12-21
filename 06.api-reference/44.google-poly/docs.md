---
title: 'Google Poly API'
taxonomy:
    category:
        - docs
---



| Methods                                  | Type   |
| ---------------------------------------- | ------  |
| GooglePoly.setAPIKey(QString key)(#m1) | void |
| GooglePoly.getAssetList(QString keyword, QString category, QString format)(#m2) | string |


## Methods


### setAPIKey()<a id="m1"></a>

Follow this link to activate your API key: https://developers.google.com/poly/develop/api. The key persists for the lifetime of the script in which it is called.

#### Function

`setAPIKey(QString key)`

#### Arguments

**key: QString**: Your Google-provided key to the Poly API

#### Example

Below is a single line usage.
```
GooglePoly.setAPIKey("0abc1def2ghi3jkl4mno5pqr6stu7vwx8yz9");
```


### getAssetList()<a id="m2"></a>

Returns a string that is JSON formatted with up to 20 assets. User can specify key words to search for

#### Function

`getAssetList(QString keyword, QString category, QString format)`

#### Arguments

**keyword: QString**: Your Google-provided key to the Poly API

#### Returns

**string**: A string that contains 

#### Example

Below is a single line usage.
```
GooglePoly.setAPIKey("0abc1def2ghi3jkl4mno5pqr6stu7vwx8yz9");
```


