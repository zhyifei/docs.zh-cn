---
title: <appSettings> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3e1c3a3cfd61a9fa8e7abdae9a25ec1bc674492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119233"
---
# <a name="clear-element-for-appsettings"></a>\<清除 \<appSettings > 元素 >

清除自定义应用程序设置。

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>特性

None

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、XML Web service Url 或任何其他自定义应用程序配置信息。 |

## <a name="child-elements"></a>子元素

None

## <a name="example"></a>示例

下面的示例演示如何清除自定义配置设置：

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](../index.md)
