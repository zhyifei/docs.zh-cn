---
title: <configSections> 的 <remove> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154525"
---
# <a name="remove-element-for-configsections"></a>\<删除>元素以\<进行配置>

删除预定义的节或节组。

[**\<配置>**](configuration-element.md)\
&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<删除>**

## <a name="syntax"></a>语法

```xml
<remove name="section name or section group name" />
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

可以使用**\<删除>** 元素从应用程序中从配置文件层次结构中较高级别定义的节和节组中删除。

## <a name="example"></a>示例

下面的示例演示如何使用应用程序配置文件中的**\<删除>** 元素来删除以前在计算机配置文件中定义的部分。

以下计算机配置文件代码声明节**\<示例节>**：

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

以下应用程序配置文件代码将删除**\<示例节>** 部分。 删除后，应用程序无法检索**\<示例节>** 中的设置。

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
