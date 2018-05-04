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
manager: markl
ms.openlocfilehash: 2d75b25734b92df062d3dc46824da44883ab46d5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
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
| [**\<运行时 >** 设置架构](~/docs/framework/configure-apps/file-schema/runtime/index.md) | 运行时设置架构中的所有元素。 |
| [**\<system.runtime.remoting >** 设置架构](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | 远程处理设置架构中的所有元素。 |
| [**\<system.Net >** 设置架构](~/docs/framework/configure-apps/file-schema/network/index.md) | 网络设置架构中的所有元素。 |
| [**\<g s >** 设置架构](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | 加密设置架构中的所有元素。 |
| [**\<配置 >** 节架构](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | 配置节设置架构中的所有元素。 |
| [跟踪和调试设置架构](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | 跟踪和调试设置架构中的所有元素。 |
| [ASP.NET 配置设置架构](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | ASP.NET 配置架构，其中包括用于配置 ASP.NET 网站和应用程序的元素中的所有元素。 在中使用*Web.config*文件。 |
| [**\<webServices >** 设置架构](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Web 服务设置架构中的所有元素。 |
| [Web 设置架构](~/docs/framework/configure-apps/file-schema/web/index.md) | Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与主机应用程序（如 IIS）一起工作的元素。 在中使用*aspnet.config*文件。 |

## <a name="remarks"></a>备注

每个配置文件必须包含恰好一个**\<配置 >** 元素。

## <a name="see-also"></a>请参阅

[.NET Framework 的配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)
