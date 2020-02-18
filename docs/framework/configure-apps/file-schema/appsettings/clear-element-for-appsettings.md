---
title: <clear> 的 <appSettings> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214814"
---
# <a name="clear-element-for-appsettings"></a>\<清除 \<appSettings > 元素 >

清除自定义应用程序设置。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>语法

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>属性

无

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | 包含自定义应用程序设置，如文件路径、XML Web service Url 或任何其他自定义应用程序配置信息。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何清除自定义配置设置：

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](../index.md)
