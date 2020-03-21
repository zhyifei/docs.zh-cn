---
title: <configuration> 的 <assemblyBinding> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155474"
---
# <a name="assemblybinding-element-for-configuration"></a>\<用于\<配置>的程序集绑定>元素

指定配置级的程序集绑定策略。

&nbsp;[**\<配置>**](configuration-element.md)&nbsp;**程序集绑定>\<**

## <a name="syntax"></a>语法

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Attribute

|           | 说明 |
| --------- | ----------- |
| **xmlns** | 必需的特性。<br><br>指定程序集绑定所需的 XML 命名空间。 使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。 |

## <a name="parent-element"></a>父元素

|     | 说明 |
| --- | ----------- |
| [**\<配置>**](configuration-element.md) | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |

## <a name="child-element"></a>子元素

|     | 说明 |
| --- | ----------- |
| [**\<链接配置>**](linkedconfiguration-element.md) | 指定要包含的配置文件。 |

## <a name="remarks"></a>备注

[**\<链接配置>**](linkedconfiguration-element.md)元素允许应用程序配置文件在已知位置包含程序集配置文件，而不是复制程序集配置设置，从而简化了组件程序集的管理。

> [!NOTE]
> 对于具有 Windows 并行清单的应用程序，不支持**\<链接的配置>** 元素。

## <a name="example"></a>示例

下面的示例演示如何在本地硬盘上包含配置文件：

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>另请参阅

- [.NET Framework 的配置文件架构](index.md)
