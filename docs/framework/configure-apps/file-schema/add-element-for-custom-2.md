---
title: '&lt;添加&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: aeb3e3a4be201369ca2df8d231498dd2400d3c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361366"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<添加 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素

添加自定义应用程序设置。 每个**\<添加 >** 标记包含键/值对。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<添加 >**

## <a name="syntax"></a>语法

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>特性

| 特性 | 描述 |
| --------- | ----------- |
| **key**   | 必需的特性。<br><br>指定设置的名称。 |
| **value** | 必需的特性。<br><br>指定设置的值。 |

## <a name="parent-element"></a>父元素

| 元素 | 描述 |
| ------- | ------------|
| [**\<sectionName >** 元素](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。 |

## <a name="child-elements"></a>子元素

无

## <a name="example"></a>示例

下面的示例演示如何定义自定义配置节以及如何使用**\<添加 >** 元素将设置放入部分：

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

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
