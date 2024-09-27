# FCL-Controllers

FCL的控制器仓库。

您可以提交拉取请求（Pull Request）以贡献代码。

## 如何上传您的控制器

请将您的 `controller.json` 文件放在
```
repo_json/<controller_id>/versions/<version_code>.json
```

将您的截图文件放在
```
repo_json/<controller_id>/screenshots/<number>.png
```

将您的 `version.json` 文件放在
```
repo_json/<controller_id>/version.json
```

将您的 `icon.png` 文件放在
```
repo_json/<controller_id>/icon.png
```

`<controller_id>` 是该控制器的ID。
`<version_code>` 是该控制器的版本代码。
`<number>` 是截图的序号，最大截图数量为16，格式应为01、02、03...16。

至少需要一张截图。

### 上传现有控制器的新版本

请确保您的PR只修改一个控制器及该控制器中的图像。

### 更新 category.json

请确保您要添加的类别在现有类别中不存在。

添加如下对象：
```
{
    "id": Example, // 整数，类别ID，例如 "0"、"1" 等。
    "lang": [
        {
            "locale": "Example", // 语言，例如 "en"、"zh_CN" 等。
            "text": "Example" // 翻译，例如 "BE style"、"基岩版" 等。
        },
        {
            "locale": "Example",
            "text": "Example"
        }
        ...
    ]
}
```
这样我们就可以在启动器中显示控制器的类别。

### 更新 index.json

添加如下对象：
```
{
    "id": "Example", // 控制器ID。
    "lang": "Example", // 控制器语言，例如 "en"、"zh_CN" 等，如果适用于所有语言，请填写 "all"。
    "name": "Example", // 控制器名称。
    "introduction": "Example", // 控制器介绍。
    "device": [
        0,
        1
    ], // 整数，0/1/2，0是手机，1是平板，2是其他设备。
    "categories": [
        0,
        1
    ] // 整数，控制器的类别。
}
```
这样我们就可以在启动器中显示控制器。

### 创建或更新 repo_json/<controller_id>/version.json

内容应为：
```
{
    "screenshot": Example, // 整数，截图数量。
    "description": "Example", // 控制器的详细描述。
    "author": "Example", // 您的名字。
    "latest": {
        "versionCode": Example, // 整数，控制器的最新版本代码，例如 "1"、"20" 等。
        "versionName": "Example" // 控制器的最新版本名称，例如 "1.0"、"2.8.5" 等。
    }, // 最新版本。
    "history": [
        {
            "versionCode": Example, // 整数，控制器的版本代码，例如 "1"、"20" 等。
            "versionName": "Example" // 控制器的版本名称，例如 "1.0"、"2.8.5" 等。
        },
        {
            "versionCode": Example,
            "versionName": "Example"
        },
        ...
    ] // 旧版本，排除最新版本。
}
```
在更新新版本时，将旧的“latest”放入“history”中，并将“latest”更改为新的版本。
同时，如果需要，您可以删除一些旧版本。

这样我们就可以在启动器中显示控制器的详细信息。
