---
title: <appSettings> 的 <add> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865c693bf8f23bf050064ac097b72aa6fa3b371e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088748"
---
# <a name="add-element-for-appsettings"></a>\<为 \<appSettings 添加 > 元素 >

添加自定义应用程序设置。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>特性

|           | 描述 |
| --------- | ----------- |
| **key**   | 必需的特性。<br><br>指定要添加的密钥的名称。 |
| **value** | 必需的特性。<br><br>指定要添加的键的值。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。 |

## <a name="child-elements"></a>子元素

None

## <a name="example"></a>示例

下面的示例演示如何为应用程序名称添加自定义配置设置：

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

下面的示例使用 `<add>` 元素定义 ASP.NET 应用程序中的两个兼容性设置：

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](../index.md)
