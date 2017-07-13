# Zendesk App - User Info, Links & Modals

_Zendesk app to support information about the user, quick custom links and modals for admin._

## Features
```
> Displays user information(configurable with custom fields).
> Provides access for custom urls to open as links and modals.
> Customizable url to different host with custom paramaters.
> Multibrand support.
```

## Development
* Zendesk App Tools (ZAT)
    * Read more [here](https://developer.zendesk.com/apps/docs/apps-v2/getting_started#zendesk-app-tools)
* Install ZAT on your local machine
    * Read more [here](https://help.zendesk.com/hc/en-us/articles/229489288)
* Zendesk App Framework v2
    * Read more [here](https://developer.zendesk.com/apps/docs/apps-v2/getting_started)

## JSON array of data for installation
* Define a simple JSON array with Brand(s), custom user fields, url and field params to access you custom pages.
* Follow the example bellow or see [json_array_demo](assets/json_array_demo.json) for a multibrand example:
````json
[
  {
    "brand": "Brand 1",
    "required_fields": [ "customField:brand_1_user_id" ],
    "data": {
      "user": [
        {
          "brand_user_id": "customField:brand_1_user_id"
        }
      ],
      "urls": [
        {
          "title": "User Edit",
          "options": ["iframe", "newtab"],
          "url": "https://www.my-domain.dk/admin/user_edit?user_id={{customField:brand_1_user_id}}"
        },
        {
          "title": "Search",
          "options": ["iframe", "newtab"],
          "url": "https://www.my-domain.dk/admin/user_search"
        }
      ]
    }
  }
]
````