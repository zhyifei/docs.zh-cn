---
title: <configuration> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: a64db49b521651ccff8b928720fe3273f8600b68
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921330"
---
# <a name="appsettings-element-for-configuration"></a>\<用于配置 > 的\<appSettings > 元素

包含自定义应用程序设置。 这是 .NET Framework 提供的预定义的配置节。

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp; **\<appSettings>**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| 文件  | 可选特性。<br><br>指定包含自定义应用程序配置设置的外部文件的相对路径。 指定的文件是否包含相同类型的设置中指定 **\<添加 >** ， **\<删除 >** ，以及 **\<清除 >** 元素，并使用同一个键/值对的格式设置为这些元素。<br><br>指定的路径相对于主配置文件。 对于 Windows 窗体应用程序, 这是二进制文件夹 (如 */bin/debug*), 而不是应用程序配置文件的位置。 对于 Web 窗体应用程序, 该路径相对于在其中找到*web.config*文件的应用程序根目录。<br><br>请注意, 如果找不到指定的文件, 则运行时将忽略属性。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**配置>\<** 元素](../configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

|     | 描述 |
| --- | ----------- |
| [ **\<add>** ](add-element-for-appsettings.md) | 添加自定义应用程序设置。 |
| [ **\<clear>** ](clear-element-for-appsettings.md) | 清除以前定义的所有应用程序设置。 |
| [ **\<remove>** ](remove-element-for-appsettings.md) | 删除以前定义的应用程序设置。 |

## <a name="remarks"></a>备注

**\<AppSettings >** 元素将自定义应用程序配置信息，如数据库连接字符串、 文件路径、 XML Web service Url 或任何其他自定义配置信息存储应用程序。 使用类<xref:System.Configuration.ConfigurationSettings>在代码中访问 **\<appSettings >** 元素中指定的键/值对。

您可以使用 web.config 的 **\<appSettings >** 元素和应用程序配置文件中的**文件**属性。 此属性指定一个配置文件, 该配置文件提供其他设置或替代在 **\<appSettings >** 元素中指定的设置。 **文件**属性可用于源代码管理团队开发方案, 例如当用户想要重写应用程序配置文件中指定的项目设置时。

指定的配置文件 **文件** 属性必须具有的根节点 **\<appSettings >** 而非 **\<配置 >** .

## <a name="example"></a>示例

下面的示例演示外部应用程序设置文件 (custom.config)，该文件定义自定义应用程序设置：

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

此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](../index.md)
