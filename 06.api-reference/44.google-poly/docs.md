---
title: 'Google Poly API'
taxonomy:
    category:
        - docs
---



| Methods                                  | Type   |
| ---------------------------------------- | ------  |
| [GooglePoly.setAPIKey(QString key)](#m1) | void |
| [GooglePoly.getAssetList(QString keyword, QString category, QString format)](#m2) | string |
| [GooglePoly.getFBX(QString keyword, QString category)](#m3) | string |
| [GooglePoly.getOBJ(QString keyword, QString category)](#m4) | string |
| [GooglePoly.getBlocks(QString keyword, QString category)](#m5) | string |


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

Returns a string that is a JSON-formatted array with up to 20 assets.

#### Function

`getAssetList(QString keyword, QString category, QString format)`

#### Arguments

**keyword: QString**: Keywords can be specified to filter assets. Multiple keywords should be separated with spaces.
<br />**category: QString**: Valid categories are: "animals, architecture, art, food, nature, objects, people, scenes, technology, transport".
<br />**format: QString**: Valid formats are: "BLOCKS, FBX, GLTF, GLTF2, OBJ, TILT".

#### Returns

**string**: A stringified version of the JSON array that Poly returns

#### Example

Below is a retrieval of an asset list after an API key has been provided.
```
var list = JSON.parse(GooglePoly.getAssetList("dog", "animals", "FBX")); /* Must use JSON.parse() to access list members */
print(JSON.stringify(list));
/* Prints an array with the following format:
[
	{
		"authorName": string,
		"createTime": string,
		"description": string,
		"displayName": string,
		"formats": [
		  	"formatComplexity": {
		    	"lodHint": number,
		    	"triangleCount": string,
		  	},
		  	"formatType": string,
		  	"resources": [
		    	{
		      		"contentType": string,
		      		"relativePath": string,
		      		"url": string,
		    	}
		  	],
		  	"root": {
				"contentType": string,
		      	"relativePath": string,
		      	"url": string,
			},
		],
		"isCurated": boolean,
		"license": enum(AssetLicense),
		"name": string,
		"presentationParams": {
		  object(PresentationParams)
		"thumbnail": {
			"contentType": string,
      		"relativePath": string,
      		"url": string,
		},
		"updateTime": string,
		"visibility": enum(Visibility),
	},
	... (up to 20 more objects) ...
]
*/
print(list[0].displayName); /* Prints the name of the first asset on the list */
```


### getFBX()<a id="m3"></a>

Returns a string that is an FBX model's URL. A model is randomly selected from the retrieved asset list that meets user-specified criteria.

#### Function

`getFBX(QString keyword, QString category)`

#### Arguments

**keyword: QString**: Keywords can be specified to filter assets. Multiple keywords should be separated with spaces.
<br />**category: QString**: Valid categories are: "animals, architecture, art, food, nature, objects, people, scenes, technology, transport".

#### Returns

**string**: The FBX model's URL.

#### Example

Below is a retrieval of an asset after an API key has been provided.
```
var model = GooglePoly.getFBX("dog", "");
Entities.addEntity({type: "Model", modelURL: model, position: Vec3.sum(MyAvatar.position, Quat.getFront(MyAvatar.orientation))}) /* A dog will rezz in front of you */
```


### getOBJ()<a id="m4"></a>

Returns a string that is an OBJ model's URL. A model is randomly selected from the retrieved asset list that meets user-specified criteria.

#### Function

`getOBJ(QString keyword, QString category)`

#### Arguments

**keyword: QString**: Keywords can be specified to filter assets. Multiple keywords should be separated with spaces.
<br />**category: QString**: Valid categories are: "animals, architecture, art, food, nature, objects, people, scenes, technology, transport".

#### Returns

**string**: The OBJ model's URL.

#### Example

Below is a retrieval of an asset after an API key has been provided.
```
var model = GooglePoly.getOBJ("cat", "");
Entities.addEntity({type: "Model", modelURL: model, position: Vec3.sum(MyAvatar.position, Quat.getFront(MyAvatar.orientation))}) /* A cat will rezz in front of you */
```


### getBlocks()<a id="m5"></a>

Returns a string that is a Blocks model's URL. A model is randomly selected from the retrieved asset list that meets user-specified criteria.

#### Function

`getBlocks(QString keyword, QString category)`

#### Arguments

**keyword: QString**: Keywords can be specified to filter assets. Multiple keywords should be separated with spaces.
<br />**category: QString**: Valid categories are: "animals, architecture, art, food, nature, objects, people, scenes, technology, transport".

#### Returns

**string**: The Blocks model's URL.

#### Example

Below is a retrieval of an asset after an API key has been provided.
```
var model = GooglePoly.getBlocks("bird", "");
Entities.addEntity({type: "Model", modelURL: model, position: Vec3.sum(MyAvatar.position, Quat.getFront(MyAvatar.orientation))}) /* A bird will rezz in front of you */
```


### getGLTF()<a id="m6"></a>

Returns a string that is a GLTF model's URL. A model is randomly selected from the retrieved asset list that meets user-specified criteria.

#### Function

`getGLTF(QString keyword, QString category)`

#### Arguments

**keyword: QString**: Keywords can be specified to filter assets. Multiple keywords should be separated with spaces.
<br />**category: QString**: Valid categories are: "animals, architecture, art, food, nature, objects, people, scenes, technology, transport".

#### Returns

**string**: The GLTF model's URL.

#### Example

Below is a retrieval of an asset after an API key has been provided.
```
var model = GooglePoly.getGLTF("snake", "");
Entities.addEntity({type: "Model", modelURL: model, position: Vec3.sum(MyAvatar.position, Quat.getFront(MyAvatar.orientation))}) /* A snake will rezz in front of you */
```