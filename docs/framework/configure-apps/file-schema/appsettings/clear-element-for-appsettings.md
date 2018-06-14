---
title: '&lt;清除&gt;元素&lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 525818309ddc142fdb3ad65ce841ea58c1d635a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350661"
---
# <a name="clear-element-for-appsettings"></a>\<清除 > 元素\<appSettings >

清除自定义应用程序设置。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<清除 >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>特性

无

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、 XML Web 服务 Url 或任何其他自定义应用程序配置信息。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何清除自定义配置设置：

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
