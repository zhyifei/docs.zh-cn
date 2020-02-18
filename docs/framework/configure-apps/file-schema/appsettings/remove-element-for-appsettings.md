---
title: <remove> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215495"
---
# <a name="remove-element-for-appsettings"></a>\<删除 \<appSettings > 元素 >

删除自定义应用程序设置。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Attribute

|         | 说明 |
| ------- | ----------- |
| **键** | 必需的特性。<br><br>指定要删除的密钥的名称。 |

### <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何删除 `ApplicationName`的自定义配置设置：

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](../index.md)
