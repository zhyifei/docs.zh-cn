---
title: <configuration> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155344"
---
# <a name="configsections-element-for-configuration"></a>\<配置>元素，用于\<配置>

包含配置部分和命名空间声明。

&nbsp;[**\<配置>**](configuration-element.md)&nbsp;**配置>\<**

## <a name="attributes"></a>属性

无

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置>**](configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

|     | 说明 |
| --- | ----------- |
| [**\<第>节**](section-element.md) | 包含配置部分声明。 |
| [**\<部分组>**](sectiongroup-element-for-configsections.md) | 为配置部分定义命名空间。 |
| [**\<删除>**](remove-element-for-configsections.md) | 删除预定义的节或节组。 |
| [**\<明确>**](clear-element-for-configsections.md) | 清除以前定义的所有节和节组。 |

## <a name="remarks"></a>备注

如果此元素位于配置文件中，则它必须是**\<配置>** 元素的第一个子元素。

## <a name="example"></a>示例

下面的示例演示如何定义配置部分并定义该部分的设置：

```xml
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

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
