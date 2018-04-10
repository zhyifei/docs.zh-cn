---
title: 与非托管代码交互操作
ms.date: 01/17/2018
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 38c569633304ed9e6f86e7a04ef7b0dfa79b6704
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="interoperating-with-unmanaged-code"></a>与非托管代码交互操作

.NET Framework 提升与 COM 组件、COM+ 服务、外部类型库和许多操作系统服务的交互。 托管和非托管对象模型之间的数据类型、方法签名和错误处理机制有所不同。 要简化 .NET Framework 组件和非托管代码之间的互操作并简化迁移路径，公共语言运行时需对客户端和服务器隐藏这些对象模型中的差异。

在运行时控制下执行的代码称为托管代码。 反之，在运行时以外运行的代码称为非托管代码。 COM 组件、ActiveX 接口和 Win32 API 函数都是非托管代码的示例。

## <a name="in-this-section"></a>本节内容

[向 .NET Framework 公开 COM 组件](exposing-com-components.md)  
描述如何使用 .NET Framework 应用程序的 COM 组件。

[向 COM 公开 .NET Framework 组件](exposing-dotnet-components-to-com.md)  
描述如何使用 COM 应用程序的 .NET Framework 组件。

[使用非托管 DLL 函数](consuming-unmanaged-dll-functions.md)  
描述如何使用平台调用调用非托管 DLL 函数。

[互操作封送处理](interop-marshaling.md)  
描述 COM 互操作和平台调用的封送处理。

[如何：映射 HRESULT 和异常](how-to-map-hresults-and-exceptions.md)  
描述异常和 HRESULT 之间的映射。

[COM 包装](com-wrappers.md)  
描述由 COM 互操作提供的包装。

[类型等效性和嵌入的互操作类型](type-equivalence-and-embedded-interop-types.md)  
描述如何将 COM 类型的类型信息嵌入在程序集中，以及公共语言运行时确定的嵌入 COM 类型等效性的方式。

[如何：使用 Tlbimp.exe 生成主互操作程序集](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
介绍如何生成使用的主互操作程序集*Tlbimp.exe* （类型库导入程序）。

[如何：注册主互操作程序集](how-to-register-primary-interop-assemblies.md)  
描述如何注册主互操作程序集，然后才能在你的项目中引用它们。

[免注册 COM 互操作](registration-free-com-interop.md)  
描述如何 COM 互操作可以激活组件，而无需使用 Windows 注册表。

[如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活](configure-net-framework-based-com-components-for-reg.md)  
描述如何创建一个应用程序清单以及如何创建和嵌入组件清单。
