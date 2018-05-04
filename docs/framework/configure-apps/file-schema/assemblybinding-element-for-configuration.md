---
title: '&lt;assemblyBinding&gt;元素&lt;配置&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6a3358b2d64ade65e641caa203e2e760dcc4be2c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding > 元素\<配置 >

指定配置级的程序集绑定策略。

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<assemblyBinding >**

## <a name="syntax"></a>语法

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>特性

|           | 描述 |
| --------- | ----------- |
| **xmlns** | 必需的特性。<br><br>指定程序集绑定所需的 XML 命名空间。 使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。 |

## <a name="parent-element"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-element"></a>子元素

|     | 描述 |
| --- | ----------- |
| [**\<linkedConfiguration >**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | 指定要包含的配置文件。 |

## <a name="remarks"></a>备注

[  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)元素中的配置文件允许应用程序配置文件包含程序集，从而简化组件程序集的管理已知位置，而不是复制的程序集配置设置。

> [!NOTE]
> **\<LinkedConfiguration >** 与 Windows 并排显示清单的应用程序中不支持元素。

## <a name="example"></a>示例

下面的示例演示如何将本地硬盘上的配置文件包括：

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
