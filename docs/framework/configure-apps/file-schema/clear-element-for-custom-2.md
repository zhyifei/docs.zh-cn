---
title: "&lt;清除&gt;NameValueSectionHandler 和 DictionarySectionHandler 元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57ee634c987d344d81f1ca099fe55e633bfbf659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<清除 > 来 NameValueSectionHandler 和 DictionarySectionHandler 元素

清除节中的所有以前定义的设置。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<清除 >**

## <a name="syntax"></a>语法

```xml
<clear />
```

## <a name="attributes"></a>特性

无

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ------------|
| [**\<sectionName >**元素](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 定义使用的自定义配置节设置<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

你可以使用**\<清除 >**元素从你在配置文件层次结构中较高级别定义的应用程序中删除所有设置。

## <a name="example"></a>示例

此示例定义计算机配置文件和应用程序配置文件，并演示如何使用**\<清除 >**清除以前中定义部分的应用程序配置文件中的元素计算机配置文件。

下面的计算机配置文件代码声明部分 **\<mySection >**:

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

下面的应用程序配置文件代码移除中的所有设置 **\<mySection >**。 应用程序无法检索任何已声明中的设置中 **\<mySection >**的计算机配置文件的部分。

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
