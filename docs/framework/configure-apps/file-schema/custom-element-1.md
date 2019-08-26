---
title: SingleTagSectionHandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927505"
---
# <a name="custom-element-for-singletagsectionhandler"></a>SingleTagSectionHandler 的自定义元素

定义自定义配置节中的设置, 该部分由\<> 元素的部分定义, <xref:System.Configuration.SingleTagSectionHandler>并使用类。

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName>*

## <a name="syntax"></a>语法

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>特性

属性和属性值是用户定义的。

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

[ **\<** ](section-element.md)  **SectionName>元素是configSections>元素中>标记\<** 部分定义的自定义元素。 [ **\<** ](configsections-element-for-configuration.md) <xref:System.Collections.IDictionary> 调用<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时, 配置系统返回对象。

## <a name="example"></a>示例

下面的示例声明一个名<xref:System.Configuration.SingleTagSectionHandler>  **\<为 sampleSection >** 的自定义元素, 该元素包含由类读取的设置:

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

此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
