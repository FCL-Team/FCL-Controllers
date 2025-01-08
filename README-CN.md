**语言：**  
[English](README.md) | **中文**

----
</br>

<h1 align="center">FCL Controllers</h1>

FCL的控制器仓库。

您可以提交拉取请求（Pull Request）以贡献代码。

## 如何上传您的控制器

1. **阅读完整的控件提交教程**
  * [FCL文档](https://fcl-team.github.io/pages/documentation.html?path=/_controller/upload_controller_zh_CN.md)
  * [腾讯文档](https://docs.qq.com/doc/DWW9QZmJZSnVhU1lD)
  * [视频](https://b23.tv/izaMGCq)

2. **加入控件审核 QQ 群**  
  **群号：139641497**
  * 禁止讨论与【控制器无关】的话题
  * 入群即问无关话题，【直接移出】
  * 未过审的键位【不要执着】于上传
  * 禁止【未经许可】地搬运键位
  * 键位上传是【纯人工】操作，请【耐心等待】

3. **上传启动器打包好的 zip 文件，等待审核**  

  * zip 文件名应为 `<controller_id>.zip`

  * zip 文件格式：
    * 请将您的 `controller.json` 文件放在
    ```
    /<controller_id>/versions/<version_code>.json
    ```
    * 将您的截图文件放在
    ```
    /<controller_id>/screenshots/<number>.png
    ```
    * 将您的 `version.json` 文件放在
    ```
    /<controller_id>/version.json
    ```
    * 将您的 `index.json` 文件放在
    ```
    /<controller_id>/index.json
    ```
    * 将您的 `icon.png` 文件放在
    ```
    /<controller_id>/icon.png
    ```

    `<controller_id>`：该控制器的ID。  
    `<version_code>`：该控制器的版本代码。  
    `<number>`：截图的序号，最大截图数量为16，格式应为01、02、03...16。  
    **请在 `index.json` 中指定 [控件类别](#控件类别)。**  
    **确保 `version.json` 和 `index.json` 格式不被破坏。**  
    **至少需要一张截图。**

## 上传现有控制器的新版本

### 方法1：群内上传

* 如欲更新控制器，直接上传即可，但要【明确告知】管理员是更新
* 键位上传是【纯人工】操作，请【耐心等待】

### 方法2：提交 PR

请确保您的 PR 只修改一个控制器及该控制器中的图像。

#### 更新 index.json

添加如下对象：
```
{
    "id": "Example", // 控制器ID。
    "lang": "Example", // 控制器语言，例如 "zh_CN"、"en" 等，如果适用于所有语言，请填写 "all"。
    "name": "Example", // 控制器名称。
    "introduction": "Example", // 控制器介绍。
    "device": [
        0, // 整数，0/1/2，0是手机，1是平板，2是其他设备。
        1
    ],
    "categories": [
        0, // 整数，控制器的类别。
        1
    ]
}
```
这样我们就可以在启动器中显示控制器。

#### 更新 version.json

文件路径：
```
repo_json/<controller_id>/version.json
```

内容应为：
```
{
    "screenshot": Example, // 整数，截图数量。
    "description": "Example", // 控制器的详细描述。
    "author": "Example", // 您的名字。
    "latest": {
        "versionCode": Example, // 整数，控制器的最新版本代码，例如 1、285 等。
        "versionName": "Example" // 控制器的最新版本名称，例如 "1.0"、"2.8.5" 等。
    }, // 最新版本。
    "history": [
        {
            "versionCode": Example, // 整数，控制器的旧版本代码。
            "versionName": "Example" // 控制器的旧版本名称。
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

## 控件类别

### 目前可用的类别如下

| 分类名称 | id | 分类描述 |
| ---- | ---- | ---- |
| 通用 | 1 | 包含所有基础功能 |
| 模组 | 2 | 针对模组做了特殊适配 |
| 仿制 | 3 | 模仿某种软件的设计语言而设计的键位 |
| PVP | 4 | 针对PVP场景做了特殊适配 |
| 全键盘 | 5 | 包含全键盘 |

### 请求添加新类别
请确保您要添加的类别在现有类别中不存在。  
记得注上相关信息，例如添加原因、分类标准、符合标准的控制器例子。
#### 方法1：在控件审核群中提出
告诉管理员你想要添加的分类及相关信息。
#### 方法2：提交 PR
记得在 PR 中填写相关信息  
请在`category.json`中添加如下对象：
```
{
    "id": Example, // 整数，类别ID，例如 1、2 等。
    "lang": [
        {
            "locale": "Example", // 语言，例如 "zh_CN"、"en" 等。
            "text": "Example" // 翻译，例如 "模组"、"Mods" 等。
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
