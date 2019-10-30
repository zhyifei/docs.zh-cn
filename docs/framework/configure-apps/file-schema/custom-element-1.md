---
title: SingleTagSectionHandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac2d01121e81b545556fb082fa7b82c31cccf9da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118838"
---
# <a name="custom-element-for-singletagsectionhandler"></a>SingleTagSectionHandler 的自定义元素

定义自定义配置节中由 \<节 > 元素定义并使用 <xref:System.Configuration.SingleTagSectionHandler> 类的设置。

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName >*

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

None

## <a name="remarks"></a>备注

**\<sectionName >** 元素是一个自定义元素，该元素由[ **\<节 >** ](section-element.md)标记在[ **\<configSections >** ](configsections-element-for-configuration.md)元素中定义。 调用 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>时，配置系统将返回 <xref:System.Collections.IDictionary> 对象。

## <a name="example"></a>示例

下面的示例声明一个名为 **\<sampleSection >** 的自定义元素，该元素包含由 <xref:System.Configuration.SingleTagSectionHandler> 类读取的设置：

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

此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
