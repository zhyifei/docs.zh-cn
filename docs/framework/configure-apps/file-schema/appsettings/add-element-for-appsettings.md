---
title: "&lt;添加&gt;元素&lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b00af6f7d735d5db8fd746205ba225253cad133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="add-element-for-appsettings"></a>\<添加 > 元素\<appSettings >

添加自定义应用程序设置。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a>特性

|           | 描述 |
| --------- | ----------- |
| **key**   | 必需的特性。<br><br>指定要添加的键的名称。 |
| **值** | 必需的特性。<br><br>指定要添加的键的值。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何添加自定义配置设置应用程序的名称：

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
