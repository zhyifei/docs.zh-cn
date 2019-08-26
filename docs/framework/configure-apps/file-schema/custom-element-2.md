---
title: NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921043"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>NameValueSectionHandler 和 DictionarySectionHandler 的自定义元素

定义使用<xref:System.Configuration.NameValueSectionHandler>和<xref:System.Configuration.DictionarySectionHandler>类的自定义配置节的设置。

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionName>**

## <a name="attributes"></a>特性

无

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-elements"></a>子元素

|     | 描述 |
| --- | ----------- |
| 为和添加 > [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler>  | 添加自定义应用程序设置。 |
| 删除和的 > [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | 删除以前定义的设置。 |
| 清除和的 > [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | 清除节中所有先前定义的设置。 |

## <a name="remarks"></a>备注

**
          \<SectionName>** 元素是通过定义的自定义元素 **\<部分>** 标记中的 **\<configSections>** 元素。

下表显示 ConfigurationSettings. GetConfig 方法为每个配置节处理程序返回的对象类型:

| 配置节处理程序                        | 返回类型                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>示例

下面的示例演示如何声明使用<xref:System.Configuration.DictionarySectionHandler>和<xref:System.Configuration.NameValueSectionHandler>类的节。

第一个自定义元素是 **\<dictionarySample >** , 它包含由`System.dll`程序集中<xref:System.Configuration.DictionarySectionHandler>的类读取的设置。 第二个自定义元素是 **\<mySection >** , 它包含由`System.dll`程序<xref:System.Configuration.NameValueSectionHandler>集中的类读取的设置。

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
