---
title: NameValueSectionHandler 和 DictionarySectionHandler 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e27bb7e21baf2eb4990d0107db4aae1b5f9a7d1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119077"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<清除 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素

清除节中所有先前定义的设置。

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>语法

```xml
<clear />
```

## <a name="attributes"></a>特性

None

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | 定义使用 <xref:System.Configuration.NameValueSectionHandler> 和 <xref:System.Configuration.DictionarySectionHandler> 类的自定义配置节的设置。 |

## <a name="child-elements"></a>子元素

None

## <a name="remarks"></a>备注

你可以使用 **\<clear >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的所有设置。

## <a name="example"></a>示例

此示例定义了计算机配置文件和应用程序配置文件，并演示了如何使用应用程序配置文件中 **\<clear >** 元素清除之前在计算机配置文件中定义的部分。

以下计算机配置文件代码声明 **\<mySection >** 部分：

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

以下应用程序配置文件代码将从 **\<mySection >** 中删除所有设置。 应用程序无法检索在计算机配置文件的 **\<mySection >** 部分的中声明的任何设置。

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
