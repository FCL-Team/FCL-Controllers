**Languages:**  
**English** | [中文](README-CN.md)

----
</br>

<h1 align="center">FCL Controllers</h1>

Controller repository of FCL.

You can submit a Pull Request to this repository to contribute.

## How to upload your controllers

1. **Read the controller uploading tutorial** (Only available in Simplified Chinese currently)
  * [FCL Doc](https://fcl-team.github.io/pages/documentation.html?path=/_controller/upload_controller.md)
  * [Tencent Document](https://docs.qq.com/doc/DWW9QZmJZSnVhU1lD) (Browser translation may not work)
  * [Video](https://b23.tv/izaMGCq)

2. **Join the controller examining QQ group**  
  **Group ID: 139641497**  
  * Discussion of topics 【unrelated to the controller】 is forbidden.
  * You will 【be kicked】 if you ask about topics unrelated to the controller.
  * Don't 【be obstinate】 with uploading unapproved controllers.
  * Upload non-original controllers 【without permission】 is forbidden.
  * Controller uploading is a 【manual operation】, please 【be patient】.

3. **Upload ZIP files packaged by the launcher and wait for being examined**  

  * ZIP file name should be `<controller_id>.zip`

  * ZIP file structure:
    * Please place your `controller.json` file at
    ```
    /<controller_id>/versions/<version_code>.json
    ```
    * Place your screenshot file at
    ```
    /<controller_id>/screenshots/<number>.png
    ```
    * Place your `version.json` file at
    ```
    /<controller_id>/version.json
    ```
    * Place your `index.json` file at
    ```
    /<controller_id>/index.json
    ```
    * Place your `icon.png` file at
    ```
    /<controller_id>/icon.png
    ```

    `<controller_id>`：the id of this controller.  
    `<version_code>`：the version code of this controller.  
    `<number>`：the serial number of the screenshot, the maximum number of screenshot is 16, it should be 01, 02, 03... 16  
    **Make sure that [controller category(s)](#controller-category) have been defined in `index.json`.**  
    **Make sure that `version.json` and `index.json` have valid JSON syntax.**  
    **At least one screenshot is required.**

## Upload a new version of an existing controller

### Method 1: Upload in QQ group

* Upload it directly in QQ group, but make sure you have 【informed the administrator】 that it's an update of an existing controller.
* Controller updating is a 【manual operation】, please 【be patient】.

### Method 2: Create pull request

Please make sure that your PR modifies only one controller, and images in that controller.

#### Update index.json

Add an object like this:
```
{
    "id": "Example", // Controller id.
    "lang": "Example", // Controller language, like "en", "zh_CN", etc, if fits all language, fill in "all".
    "name": "Example", // Name of the controller.
    "introduction": "Example", // Introduction of the controller.
    "device": [
        0, // Integer, 0/1/2, 0 is phone, 1 is pad, 2 is other device.
        1
    ],
    "categories": [
        0, // Integer, categories of the controller.
        1
    ]
}
```
So we can display the controller in the launcher.

#### Update version.json

File path：
```
repo_json/<controller_id>/version.json
```

File content：
```
{
    "screenshot": Example, // Integer, number of the screenshots.
    "description": "Example", // Detailed description of the controller.
    "author": "Example", // Your name.
    "latest": {
        "versionCode": Example, // Integer, latest version code of controller, like 1, 285, etc.
        "versionName": "Example" // Latest version name of controller, like "1.0", "2.8.5", etc.
    }, // Latest version.
    "history": [
        {
            "versionCode": Example, // Integer, version code of controller.
            "versionName": "Example" // Version name of controller.
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

## Controller category

### Available categories:

| Name | ID | Categorie description |
| ---- | ---- | ---- |
| Universal | 1 | Contains all basic features |
| Mods | 2 | Adapts to some mods |
| Imitate | 3 | Imitates controllers of another software |
| PVP | 4 | Adapts to PVP games |
| Full keyboard | 5 | Contains full keyboard |
| Style | 6 | Provide button styles for other controller makers |

### Request for a new category
Make sure the new category doesn't exist.  
Remember to note related information, such as reason of adding the categories, the classifying standard, and examples of controllers that meet the standard.
#### Method 1: Ask in QQ group
Tell your administrator the categories and related information you want to add.
#### Method 2: Create pull request
Add related information in the pull request.  
Add an object in `category.json` like this:
```
{
    "id": Example, // Integer, category id, like 1, 2, etc.
    "lang": [
        {
            "locale": "Example", // Language, like "en", "zh_CN", etc.
            "text": "Example" // Translation, like "Mods", "模组", etc.
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
