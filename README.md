[中文](README-CN.md)

# FCL-Controllers

Controller repository of FCL.

You can submit a Pull Request to this repository to contribute.

## How to upload your controllers

Please place your controller.json file at
```
repo_json/<controller_id>/versions/<version_code>.json
```

Place your screenshot file at
```
repo_json/<controller_id>/sceenshots/<number>.png
```

Place your version.json file at
```
repo_json/<controller_id>/version.json
```

Place your icon.png file at
```
repo_json/<controller_id>/icon.png
```

`<controller_id>` is the id of this controller.
`<version_code>` is the version code of this controller.
`<number>` is the serial number of the screenshot, the maximum number of screenshot is 16, it should be 01, 02, 03... 16.

At least one screenshot.

### Upload a new version of an existing controller

Please make sure that your PR modifies only one controller, and images in that controller.

### Update category.json

Please ensure that the category you want to add is not already in the existing categories.

Add an object like this:
```
{
    "id": Example, // Integer, category id, like "0", "1", etc.
    "lang": [
        {
            "locale": "Example", // Language, like "en", "zh_CN", etc.
            "text": "Example" // Translation, like "BE style", "基岩版", etc.
        },
        {
            "locale": "Example",
            "text": "Example"
        }
        ...
    ]
}
```
So we can display the category of the controller in the launcher.

### Update index.json

Add an object like this:
```
{
    "id": "Example", // Controller id.
    "lang": "Example", // Controller language, like "en", "zh_CN", etc, if fits all language, fill in "all".
    "name": "Example", // Name of the controller.
    "introduction": "Example", // Introduction of the controller.
    "device": [
        0,
        1
    ], // Integer, 0/1/2, 0 is phone, 1 is pad, 2 is other device.
    "categories": [
        0,
        1
    ] // Integer, categories of the controller.
}
```
So we can display the controller in the launcher.

### Create or update repo_json/<controller_id>/version.json

The content should be:
```
{
    "screenshot": Example, // Integer, number of the screenshots.
    "description": "Example", // Detailed description of the controller.
    "author": "Example", // Your name.
    "latest": {
        "versionCode": Example, // Integer, latest version code of controller, like "1", "20", etc.
        "versionName": "Example" // Latest version name of controller, like "1.0", "2.8.5", etc.
    }, // Latest version.
    "history": [
        {
            "versionCode": Example, // Integer, version code of controller, like "1", "20", etc.
            "versionName": "Example" // Version name of controller, like "1.0", "2.8.5", etc.
        },
        {
            "versionCode": Example,
            "versionName": "Example"
        },
        ...
    ] // Old versions, excluding latest version.
}
```
When update a new version, put the old "latest" into "history", and change the "latest" to the new one.
Also, you can delete some old versions if you want.

So we can display the details of the controller in the launcher.
