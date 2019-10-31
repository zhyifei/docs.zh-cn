---
title: <configSections> 的 <remove> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f57dc9279c107ce751f71c2998670ab992db162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118440"
---
# <a name="remove-element-for-configsections"></a>\<删除 \<configSections > 元素 >

删除预定义的节或节组。

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**

## <a name="syntax"></a>语法

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| **name**  | 必需的特性。<br><br>指定要删除的节或节组的名称。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<configSections >** Element](configsections-element-for-configuration.md) | 包含配置节和命名空间声明。 |

## <a name="child-elements"></a>子元素

None

## <a name="remarks"></a>备注

你可以使用 **\<remove >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的部分和节组。

## <a name="example"></a>示例

下面的示例演示如何使用应用程序配置文件中的 **\<remove >** 元素删除之前在计算机配置文件中定义的部分。

以下计算机配置文件代码声明 **\<sampleSection >** 部分：

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

以下应用程序配置文件代码将删除 **\<sampleSection >** 部分。 删除后，应用程序无法检索 **\<sampleSection >** 中的设置。

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*

## <a name="see-also"></a>请参阅

- [.NET Framework 的配置文件架构](index.md)
