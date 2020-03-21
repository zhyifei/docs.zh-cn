---
title: <configuration> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155526"
---
# <a name="appsettings-element-for-configuration"></a>\<用于\<配置>的应用设置>元素

包含自定义应用程序设置。 这是由 .NET 框架提供的预定义配置部分。

&nbsp;[**\<配置>**](../configuration-element.md)&nbsp;**应用设置>\<**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attribute

|           | 说明 |
| --------- | ----------- |
| **文件**  | 可选特性。<br><br>指定包含自定义应用程序配置设置的外部文件的相对路径。 指定的文件包含在**\<添加>、****\<删除>** 和**\<清除>** 元素中指定的相同类型的设置，并使用与这些元素相同的键/值对格式。<br><br>指定的路径与主配置文件相关。 对于 Windows 窗体应用程序，这是二进制文件夹（如 */bin/调试*），而不是应用程序配置文件的位置。 对于 Web 窗体应用程序，路径相对于*Web.config*文件所在的应用程序根。<br><br>如果找不到指定的文件，运行时将忽略该属性。 |

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置>** 元素](../configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

|     | 说明 |
| --- | ----------- |
| [**\<添加>**](add-element-for-appsettings.md) | 添加自定义应用程序设置。 |
| [**\<明确>**](clear-element-for-appsettings.md) | 清除以前定义的所有应用程序设置。 |
| [**\<删除>**](remove-element-for-appsettings.md) | 删除以前定义的应用程序设置。 |

## <a name="remarks"></a>备注

appSettings>元素存储自定义应用程序配置信息，如数据库连接字符串、文件路径、XML Web 服务 URL 或应用程序的任何其他自定义配置信息。 ** \<** 使用<xref:System.Configuration.ConfigurationSettings>类在代码中访问**\<appSettings>** 元素中指定的键/值对。

您可以在**\<AppSettings>** *Web.config*和应用程序配置文件的元素中使用**文件**属性。 此属性指定提供其他设置或覆盖**\<appSettings>** 元素中指定的设置的配置文件。 **文件**属性可用于源代码管理团队开发方案，例如当用户想要覆盖应用程序配置文件中指定的项目设置时。

**文件**属性指定的配置文件必须具有**\<appSettings>** 的根节点，而不是**\<配置>。 **

## <a name="example"></a>示例

下面的示例演示外部应用程序设置文件 (custom.config**)，该文件定义自定义应用程序设置：

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

下面的示例演示使用外部设置文件中的设置并自行设置应用程序设置的应用程序配置文件：

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](../index.md)
