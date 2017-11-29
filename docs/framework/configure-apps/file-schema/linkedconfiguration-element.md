---
title: "&lt;linkedConfiguration&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bfea438ec19303c35ad9d7a2816cb7b9473a00c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > 元素

指定要包含的配置文件。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**

## <a name="syntax"></a>语法

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| **href**  | 必需的特性。<br><br>要包括的配置文件的 URL。 有关支持的唯一格式**href**属性是`file://`。 支持本地文件和 UNC 文件。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<assemblyBinding >**元素](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | 指定配置级的程序集绑定策略。 |

## <a name="child-elements"></a>子元素

无

## <a name="remarks"></a>备注

**\<LinkedConfiguration >**元素简化了维护的组件程序集。 如果一个或多个应用程序使用具有配置文件中的已知位置的程序集，可以使用的应用程序使用的程序集的配置文件 **\<linkedConfiguration >**元素以包含程序集配置文件，而不是直接包含配置信息。 组件程序集已维修，更新常见的配置文件提供所有应用程序使用的程序集的更新的配置的信息。

> [!NOTE]
> **\<LinkedConfiguration >**与 Windows 并排显示清单的应用程序中不支持元素。

以下规则控制的链接的配置文件的使用：

- 包含的配置文件中的设置仅影响加载程序绑定策略，并只由加载程序。 包含的配置文件可以设置而非绑定策略，但这些设置不产生任何影响。

- 有关支持的唯一格式`href`属性是`file://`。 支持本地文件和 UNC 文件。

- 不没有链接配置每个配置文件数受任何约束。

- 所有链接的配置文件合并，以形成一个文件的行为类似`#include`C/c + + 中的指令。

- **\<LinkedConfiguration >**元素允许仅在应用程序配置文件中; 在将被忽略*Machine.config*。

- 检测和终止循环引用。 也就是说，如果 **\<linkedConfiguration >**的一系列的配置文件的元素形成循环，循环是检测到，并已停止。

## <a name="example"></a>示例

下面的示例演示如何将从本地硬盘上的配置文件包括：

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>请参阅

[**\<assemblyBinding >**元素](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
