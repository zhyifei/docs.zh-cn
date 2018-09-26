---
title: '&lt;配置&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 40c0ab5f18d5aae2c99dd66747d3435f0826af8b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171265"
---
# <a name="configuration-element"></a>\<配置 > 元素

公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。

**\<configuration>**

## <a name="syntax"></a>语法

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>特性

无

## <a name="parent-element"></a>父元素

无

## <a name="child-elements"></a>子元素

|     | 描述 |
| --- | ----------- |
| [**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | 指定配置级的程序集绑定策略。|
| [**\<启动 >** 设置架构](~/docs/framework/configure-apps/file-schema/startup/index.md) | 启动设置架构中的所有元素。 |
| [**\<运行时 >** 设置架构](~/docs/framework/configure-apps/file-schema/runtime/index.md) | 在运行时设置架构中的所有元素。 |
| [**\<system.runtime.remoting >** 设置架构](https://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | 远程处理设置架构中的所有元素。 |
| [**\<system.Net >** 设置架构](~/docs/framework/configure-apps/file-schema/network/index.md) | 网络设置架构中的所有元素。 |
| [**\<cryptographySettings >** 设置架构](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | 加密设置架构中的所有元素。 |
| [**\<配置 >** 节架构](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | 配置部分设置架构中的所有元素。 |
| [跟踪和调试设置架构](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | 跟踪和调试设置架构中的所有元素。 |
| [ASP.NET 配置设置架构](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | 在 ASP.NET 配置架构中，其中包括用于配置 ASP.NET 网站和应用程序的元素的所有元素。 在中使用*Web.config*文件。 |
| [**\<web 服务 >** 设置架构](https://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Web 服务设置架构中的所有元素。 |
| [Web 设置架构](~/docs/framework/configure-apps/file-schema/web/index.md) | Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与主机应用程序（如 IIS）一起工作的元素。 在中使用*aspnet.config*文件。 |

## <a name="remarks"></a>备注

每个配置文件必须包含一个**\<配置 >** 元素。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
