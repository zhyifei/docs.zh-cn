---
title: NameValueSectionHandler 和 DictionarySectionHandler 的 <add> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215441"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<添加 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素

添加自定义应用程序设置。 每个 **\<添加 >** 标记包含一个键/值对。

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**

## <a name="syntax"></a>语法

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>属性

| Attribute | 说明 |
| --------- | ----------- |
| **键**   | 必需的特性。<br><br>指定设置的名称。 |
| **value** | 必需的特性。<br><br>指定设置的值。 |

## <a name="parent-element"></a>父元素

| 元素 | 说明 |
| ------- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | 定义使用 <xref:System.Configuration.NameValueSectionHandler> 和 <xref:System.Configuration.DictionarySectionHandler> 类的自定义配置节的设置。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何定义自定义配置节，并使用 **\<添加 >** 元素将设置放入部分：

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
