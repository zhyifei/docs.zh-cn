---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153720"
---
# <a name="section-element"></a>\<节>元素

包含配置部分声明。

[**\<配置>**](configuration-element.md)\
&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<第>节**

[**\<配置>**](configuration-element.md)\
&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<部分组>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<第>节**

## <a name="syntax"></a>语法

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>必需属性

|           | 说明 |
| --------- | ----------- |
| **name**  | 指定配置部分的名称。 |
| **type**  | 指定从配置文件读取节的配置节处理程序类的名称。 类型值具有语法"完全限定的截面处理程序-类名称，简单程序集名称"。 简单的程序集名称是没有 *.dll*文件扩展名的根文件名。 |

## <a name="optional-attributes"></a>可选属性

以下属性仅适用于ASP.NET应用程序。 配置系统忽略这些属性的其他应用程序类型。

|                     | 说明 |
| ------------------- | ----------- |
| **允许定义** | 指定该节可以使用的配置文件。 使用以下值之一：<br><br>**无处不在**<br>允许在任何配置文件中使用该节。 这是默认值。<br>**仅限机器**<br>允许仅在机器配置文件 （*机器.config）* 中使用该部分。<br>**机器应用**<br>允许在计算机配置文件或应用程序配置文件中使用节。 |
| **允许定位**   | 确定是否可以在**\<位置>** 元素中使用节。 使用以下值之一：<br><br>**true**<br>允许在**\<位置>** 元素中使用节。 这是默认值。<br>**false**<br>不允许在**\<位置>** 元素中使用节。 |

## <a name="parent-elements"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置部分>** 元素](configsections-element-for-configuration.md) | 包含配置部分和命名空间声明。 |
| [第>节组**\<** 元素](sectiongroup-element-for-configsections.md) | 为配置部分定义命名空间。 |

> [!NOTE]
> ** \<>元素的节**是**\<配置">"** 或**\<"组组">** 的子元素，但不能同时提供两者。

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

声明配置部分实质上定义配置文件的新元素。 新元素包含配置节处理程序（即实现接口的类）读取的<xref:System.Configuration.IConfigurationSectionHandler>设置。 定义的节的属性和子元素取决于用于读取设置的节处理程序。

在*Machine.config 文件中*声明配置部分处理程序使您能够在该计算机上的任何应用程序配置文件中使用配置节，除非**allowDefinition**属性另有指定。

## <a name="example"></a>示例

下面的示例演示如何定义配置部分并定义该部分的设置：

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
