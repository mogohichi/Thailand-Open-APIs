# Introduction
The Thailand Open APIs was created aiming to provide a better way to access Thailand Open Data.


##### API Endpoint
https://api.openthailand.org/

##### Supported Methods
GET | POST | DELETE | PUT


##### Authentication
There is no authentication required at this point.

##### API Request Format
Thailand Open API request takes the following form:

https://api.openthailand.org/<b>resource</b>?<b>parameters</b>

Required and optional parameters will be described in each endpoint if any.

##### Success Response Format
```json
{
	"code":200,
	"result":{}
}
```

##### Error Response Format
```json
{
	"code":400,
	"error":{
		"message":"BAD REQUEST"
	}
}
```



# Endpoints

#### Get all Thailand provinces
Retrieve all provinces.

> GET https://api.openthailand.org/provinces

**Sample JSON Response**
```js
{
	"code":200,
	"result":{ 
		"data":[
				{
					"id":"chonburi",
					"name":"Chonburi",
					"name_th":"ชลบุรี"
				},
				{
					"id":"bangkok",
					"name":"Bangkok",
					"name_th":"กรุงเทพฯ"
				}
			]
		}
}
```
- - -
#### Get all districts in province
Retrieve all districts(amphor) of given province.
> GET https://api.openthailand.org/provinces/<b>{province_id}</b>/districts

**Required parameters**  
`province_id` — id of province

**Sample Request**
> GET https://api.openthailand.org/provinces/<b>chonburi</b>/districts

**Sample JSON Response**
```js
{
	"code":200,
	"result":{ 
		"province":{
			"id":"chonburi",
			"name":"Chonburi",
			"name_th":"ชลบุรี"
		},
		"data":[
				{
					"id":"1",
					"name":"Si Racha",
					"name_th":"ศรีราชา"
				},
				{
					"id":"2",
					"name":"Bang Sean",
					"name_th":"บางแสน"
				}
			]
		}
}
```
- - -
#### Get all subdistricts in district in province
Retrieve all subdistricts(tambon) of given district(amphor) in province.
> GET https://api.openthailand.org/provinces/<b>{province_id}</b>/districts/<b>{district_id}</b>/subdistricts

**Required parameters**  
`province_id` — id of province  
`district_id` — id of district

**Sample Request**
> GET https://api.openthailand.org/provinces/<b>chonburi</b>/districts/<b>1</b>/subdistricts

**Sample JSON Response**
```js
{
	"code":200,
	"result":{ 
		"province":{
			"id":"chonburi",
			"name":"Chonburi",
			"name_th":"ชลบุรี"
		},
		"district":{
			"id":"1",
			"name":"Sriracha",
			"name_th":"ศรีราชา"
		},
		"data":[
				{
					"id":"1",
					"name":"Si Racha",
					"name_th":"ศรีราชา",
					"location": {
						"lat": 13.162,
						"lng": 100.923
					}
				},
				{
					"id":"2",
					"name":"Surasak",
					"name_th":"สุรศักดิ์",
					"location": {
						"lat": 13.160,
						"lng": 100.983
					}
				}
			]
		}
}
```

- - -
### Sponsored by
Mogohichi, Inc.
