---
title: "将 COM 的程序集打包 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET 服务安装工具"
  - "程序集注册工具"
  - "COM 互操作, 公开 COM 组件"
  - "COM 互操作, 打包程序集"
  - "向 COM 公开 .NET Framework 组件"
  - "与非托管代码间的互操作, 公开 .NET Framework 组件"
  - "与非托管代码间的互操作, 打包程序集"
  - "为 COM 打包程序集"
  - "Reqasm.exe"
  - "Reqsvcs.exe"
  - "Tlbexp.exe"
  - "类型库导出程序"
  - "TypeLibConverter 类"
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 将 COM 的程序集打包
以下有关托管类型的信息将使要将这些类型包含在其应用程序中的 COM 开发人员受益：  
  
-   COM 应用程序可使用的类型的列表  
  
     有些托管类型对于 COM 不可见；有些可见但无法创建；还有些既可见又可创建。  程序集可以包括不可见、可见、无法创建和可创建类型的任意组合。  为了确保完整性，应确定程序集中要向 COM 公开的类型，尤其是当这些类型是要向 .NET Framework 公开的类型子集时。  
  
     有关其他信息，请参见[为互用性限定 .NET 类型](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)。  
  
-   版本控制指南  
  
     实现类接口（由 COM 互操作生成的接口）的托管类会受到版本控制的限制。  
  
     有关如何使用这些类接口的指南，请参见[类接口简介](http://msdn.microsoft.com/zh-cn/733c0dd2-12e5-46e6-8de1-39d5b25df024)。  
  
-   部署指南  
  
     由发行者签名并带有强名称的程序集可以安装到全局程序集缓存中。  未签名的程序集必须作为专用程序集安装在用户的计算机上。  
  
     有关其他信息，请参见[程序集安全注意事项](../../../docs/framework/app-domains/assembly-security-considerations.md)。  
  
-   类型库包含  
  
     大多数类型在由 COM 应用程序使用时，都需要类型库。  您可以生成一个类型库或让 COM 开发人员执行此任务。  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 为生成类型库提供了下列选项：  
  
    -   [类型库导出程序](#cpconpackagingassemblyforcomanchor1)  
  
    -   [TypeLibConverter 类](#cpconpackagingassemblyforcomanchor2)  
  
    -   [程序集注册工具](#cpconpackagingassemblyforcomanchor3)  
  
    -   [.NET 服务安装工具](#cpconpackagingassemblyforcomanchor4)  
  
     无论您选择哪种机制，只有在您提供的程序集中定义的公共类型才会包括在生成的类型库中。  
  
     可以将类型库包装为单独的文件或将其作为 Win32 资源文件嵌入到基于 .NET 的应用程序中。  Microsoft Visual Basic 6.0 为您自动执行此任务；但是，在使用 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] 时，必须手动嵌入类型库。  有关说明，请参见[如何：将类型库作为 Win32 资源嵌入到基于 .NET 的应用程序中](http://msdn.microsoft.com/zh-cn/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)。  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## 类型库导出程序  
 [类型库导出程序 \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 是一种命令行工具，它用于将包含在程序集中的类和接口转换为 COM 类型库。  当类的类型信息成为可用时，COM 客户端就可以创建 .NET 类的一个实例并调用该实例的方法，就好像它是 COM 对象一样。  Tlbexp.exe 将同时转换整个程序集。  不能使用 Tlbexp.exe 生成程序集中定义的类型子集的类型信息。  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## TypeLibConverter 类  
 位于 **System.Runtime.Interop** 命名空间的 <xref:System.Runtime.InteropServices.TypeLibConverter> 类可将包含在程序集中的类和接口转换为 COM 类型库。  此 API 与上节所述的类型库导出程序生成相同的类型信息。  
  
 **TypeLibConverter class** 实现 [ITypeLibConverter 接口](frlrfSystemRuntimeInteropServicesITypeLibConverterClassTopic)。  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## 程序集注册工具  
 当应用 **\/tlb:** 选项时，[程序集注册工具 \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 可生成并注册类型库。  COM 客户端要求将类型库安装在 Windows 注册表中。  如果不使用此选项，Regasm.exe 将只注册程序集（而不是类型库）中的类型。  注册程序集中的类型和注册类型库是截然不同的活动。  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## .NET 服务安装工具  
 [.NET 服务安装工具 \(Regsvcs.exe\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md) 可将托管类添加到 Windows 2000 组件服务中，并在一个工具中组合了多项任务。  除了加载和注册程序集之外，Regsvcs.exe 还可以生成、注册类型库并将其安装到现有的 COM\+ 1.0 应用程序中。  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [为互操作限定 .NET 类型](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/zh-cn/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [程序集安全注意事项](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe（类型库导出程序）](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [向 COM 注册程序集](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [How to: Embed Type Libraries as Win32 Resources in Applications](http://msdn.microsoft.com/zh-cn/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)