---
title: "&lt;部分&gt;元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8ed8b0211c8366d799fe158d91dcb42f92ad0cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="section-element"></a>\<部分 > 元素

包含配置节声明。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<部分 >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<部分 >**

## <a name="syntax"></a>语法

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>必需的特性

|           | 描述 |
| --------- | ----------- |
| **name**  | 指定的配置节的名称。 |
| **type**  | 指定从配置文件中读取节的配置节处理程序类的名称。 类型值具有语法"fully-qualified-section-handler-class-name，简单程序集名称"。 简单程序集名称是根文件名无*.dll*文件扩展名。 |

## <a name="optional-attributes"></a>可选特性

以下属性是仅适用于 ASP.NET 应用程序。 配置系统会忽略这些属性对于其他应用程序类型。

|                     | 描述 |
| ------------------- | ----------- |
| **allowDefinition** | 指定可以在使用的节的配置文件。 使用下列值之一：<br><br>**无处不在**<br>允许在任何配置文件中使用该节。 这是默认设置。<br>**MachineOnly**<br>允许仅在计算机配置文件中使用该节 (*Machine.config*)。<br>**MachineToApplication**<br>允许要在计算机配置文件或应用程序配置文件中使用的部分。 |
| **allowLocation**   | 确定是否可以在使用的部分**\<位置 >**元素。 使用下列值之一：<br><br>**true**<br>允许要在中使用该节**\<位置 >**元素。 这是默认设置。<br>**false**<br>不允许在中使用的部分**\<位置 >**元素。 |

## <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<configSections >**元素](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 包含配置节和命名空间声明。 |
| [**\<sectionGroup >**元素](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | 定义配置节的命名空间。 |

> [!NOTE]
> A **\<部分 >**元素是其中任何一个子元素 **\<configSections >**或 **\<sectionGroup >**但不是两者。

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

实质上声明配置节定义配置文件的新元素。 新元素包含一个配置节处理程序的设置 (即，一个类以实现<xref:System.Configuration.IConfigurationSectionHandler>接口) 读取。 属性和你定义的节的子元素取决于你使用读取你的设置节处理程序。

声明中的配置节处理程序*Machine.config*文件，您可以在该计算机上任何应用程序配置文件中使用的配置部分除非**allowDefinition**属性指定，否则。

## <a name="example"></a>示例

下面的示例演示如何定义一个配置节和定义该部分的设置：

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

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
