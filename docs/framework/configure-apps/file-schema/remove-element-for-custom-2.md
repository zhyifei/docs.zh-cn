---
title: '&lt;删除&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<删除 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素

删除以前定义的设置。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<删除 >**

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
| [**\<sectionName >** 元素](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

你可以使用**\<删除 >** 元素以删除从应用程序在配置文件层次结构中较高级别定义的设置。

## <a name="example"></a>示例

下面的示例演示如何使用**\<删除 >** 删除先前在计算机配置文件中定义的设置的应用程序配置文件中的元素。

下面的计算机配置文件代码声明部分 **\<mySection >** 并添加两个设置`key1`和`key2`，到它：

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

下面的应用程序配置文件代码移除`key2`设置从 **\<mySection >**:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
