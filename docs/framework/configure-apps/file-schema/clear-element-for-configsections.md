---
title: <configSections> 的 <clear> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155422"
---
# <a name="clear-element-for-configsections"></a>\<用于\<配置>的透明>元素

清除以前定义的所有节和节组。

&nbsp;[**\<配置>**](configuration-element.md)&nbsp;&nbsp;**配置>\<清晰的>** [** \<**](configsections-element-for-configuration.md) &nbsp; &nbsp; &nbsp;

## <a name="syntax"></a>语法

```xml
<clear/>
```

## <a name="attribute"></a>Attribute

|           | 说明 |
| --------- | ----------- |
| **name**  | 必需的特性。<br><br>指定要删除的节或节组的名称。 |

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置部分>** 元素](configsections-element-for-configuration.md) | 包含配置部分和命名空间声明。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

**\<清除>** 元素从应用程序中删除当前配置文件前面或配置文件层次结构中较高级别定义的所有节和节组。

## <a name="example"></a>示例

本示例定义计算机配置文件和应用程序配置文件，并演示如何在应用程序配置文件中使用**\<清除>** 元素来清除以前在计算机配置文件中定义的部分。

以下计算机配置文件代码声明两个部分，**\<示例节>****\<和另一个Sample节>**，在应用程序配置文件之前读取：

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

以下应用程序配置文件代码清除以前声明的所有部分。 应用程序无法使用或检索在计算机配置文件中声明的任一部分中的设置。 但是，它可以使用**\<另一节>** 设置，因为它在**\<明确>** 元素之后出现。

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

此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
