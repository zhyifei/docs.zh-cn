---
title: NameValueSectionHandler 和 DictionarySectionHandler 的 <remove> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc1519a794e24e04074dd2a674ecc2c0f3666521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118563"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<删除 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素

删除以前定义的设置。

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**

## <a name="syntax"></a>语法

```xml
<add remove="key" />
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| **key**   | 必需的特性。<br><br>指定要删除的设置的名称。 |

## <a name="parent-element"></a>父元素

| 元素 | 描述 |
| ------- | ------------|
| [ **\<sectionName >** Element](custom-element-2.md) | 定义使用 <xref:System.Configuration.NameValueSectionHandler> 和 <xref:System.Configuration.DictionarySectionHandler> 类的自定义配置节的设置。 |

## <a name="child-elements"></a>子元素

None

## <a name="remarks"></a>备注

你可以使用 **\<remove >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的设置。

## <a name="example"></a>示例

下面的示例演示如何使用应用程序配置文件中的 **\<remove >** 元素删除以前在计算机配置文件中定义的设置。

以下计算机配置文件代码声明 **\<mySection >** 部分，并将两个设置（`key1` 和 `key2`）添加到其中：

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

以下应用程序配置文件代码将从 **\<mySection >** 中删除 `key2` 设置：

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
