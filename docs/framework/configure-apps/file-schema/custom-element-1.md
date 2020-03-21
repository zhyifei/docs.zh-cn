---
title: 单一标签节处理程序的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155149"
---
# <a name="custom-element-for-singletagsectionhandler"></a>单一标签节处理程序的自定义元素

在由\<节>元素定义的自定义配置部分中定义设置，并使用类<xref:System.Configuration.SingleTagSectionHandler>。

&nbsp;[**\<配置>**](configuration-element.md)&nbsp;*节名称>\<*

## <a name="syntax"></a>语法

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>属性

属性和属性值是用户定义的。

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置>**](configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

**\<节名称>** 元素是由[**\<配置节>**](configsections-element-for-configuration.md)元素中[**\<>**](section-element.md)标记定义的自定义元素。 当您调用<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时，<xref:System.Collections.IDictionary>配置系统将返回一个对象。

## <a name="example"></a>示例

以下示例声明一个称为**\<示例节>** 的自定义元素，其中包含类读取的<xref:System.Configuration.SingleTagSectionHandler>设置：

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
