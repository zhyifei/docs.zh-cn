---
title: "自定义元素 SingleTagSectionHandler"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ee722c7d5db9d58ab1a91f4b1299912981510af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="custom-element-for-singletagsectionhandler"></a>自定义元素 SingleTagSectionHandler

在定义的自定义配置节中定义设置 <section> 元素，并使用<xref:System.Configuration.SingleTagSectionHandler>类。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;*\<sectionName >*

## <a name="syntax"></a>语法

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>特性

属性和属性值是用户定义的。

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

 **\<SectionName >**元素是由定义的自定义元素[ **\<部分 >** ](~/docs/framework/configure-apps/file-schema/section-element.md)中标记[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)元素。 配置系统返回<xref:System.Collections.IDictionary>对象在调用时<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>。

## <a name="example"></a>示例

下面的示例声明一个名为自定义元素 **\<sampleSection >**包含设置读取<xref:System.Configuration.SingleTagSectionHandler>类：

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

此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
