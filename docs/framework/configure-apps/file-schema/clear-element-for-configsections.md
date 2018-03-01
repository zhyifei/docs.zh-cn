---
title: "&lt;清除&gt;元素&lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e48887cf7e227f463b92edd50f69746bbd8abd0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-configsections"></a>\<清除 > 元素\<configSections >

清除所有以前定义的节和节组。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<清除 >**

## <a name="syntax"></a>语法

```xml
<clear/>
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| **name**  | 必需的特性。<br><br>指定的节或要删除的部分组的名称。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<configSections >**元素](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 包含配置节和命名空间声明。 |

# <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

**\<清除 >**元素从你当前的配置文件中或在配置文件层次结构中较高级别前面定义的应用程序中删除所有节和节组。

## <a name="example"></a>示例

此示例定义计算机配置文件和应用程序配置文件，并演示如何使用**\<清除 >**清除以前中定义部分的应用程序配置文件中的元素计算机配置文件。

下面的计算机配置文件代码声明两个部分，  **\<sampleSection >**和 **\<anotherSampleSection >**，这应用程序之前，读取配置文件：

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

下面的应用程序配置文件代码清除所有以前声明的节。 应用程序不能使用或检索中的各个部分的计算机配置文件中声明的设置。 但是，它可以使用从设置 **\<anotherSection >**因为它之后**\<清除 >**元素。

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
