---
title: "向 COM 注册程序集 | Microsoft Docs"
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
  - "COM 互操作, 注册程序集"
  - "与非托管代码间的互操作, 注册程序集"
  - "注册程序集"
  - "注销程序集"
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 向 COM 注册程序集
您可以运行一个叫做[程序集注册工具 \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 的命令行工具来注册或注销与 COM 一起使用的程序集。  Regasm.exe 添加有关选件类的信息向系统注册表，以便 COM 客户端可以透明地使用 .NET framework 选件类。  <xref:System.Runtime.InteropServices.RegistrationServices> 类提供了等效的功能。  
  
 必须先在 Windows 注册表中注册托管组件，然后才可以从 COM 客户端将其激活。  下表显示 Regasm.exe 通常添加到 Windows 注册表中的注册表项。  （000000 指示实际 GUID 值。）  
  
|GUID|描述|注册表项|  
|----------|--------|----------|  
|CLSID|类标识符|HKEY\_CLASSES\_ROOT\\CLSID\\{000…000}|  
|IID|接口标识符|HKEY\_CLASSES\_ROOT\\Interface\\{000…000}|  
|LIBID|库标识符|HKEY\_CLASSES\_ROOT\\TypeLib\\{000…000}|  
|ProgID|编程标识符|HKEY\_CLASSES\_ROOT\\000…000|  
  
 在 HKCR\\CLSID\\{0000…0000} 项下，默认值设置为类的 ProgID，并且会添加两个新的命名值：“类”值和“程序集”值。  运行时将从注册表中读取“程序集”值，并将其传递给运行时程序集冲突解决程序。  程序集冲突解决程序将根据程序集信息（如名称和版本号）尝试查找程序集。  为便于程序集冲突解决程序查找程序集，程序集必须位于以下某一位置中：  
  
-   全局程序集缓存（必须是强名称的程序集）。  
  
-   在应用程序目录中。  从应用程序路径加载的程序集只能通过该应用程序进行访问。  
  
-   沿使用 **\/codebase** 选项指定的、指向 Regasm.exe 的文件路径。  
  
 Regasm.exe 还会在 HKCR\\CLSID\\{0000…0000} 项下创建 InProcServer32 项。  该键的默认值设置为初始化公共语言运行时的 DLL 的名称 \(Mscoree.dll\)。  
  
## 检查注册表项  
 COM 互操作提供了标准的类工厂实现来创建任何 .NET Framework 类的实例。  客户端可以通过对托管 DLL 调用 **DllGetClassObject** 来获取类工厂并创建对象，就像处理其他任何 COM 组件一样。  
  
 为 `InprocServer32` 子级，对 Mscoree.dll 的引用将一个替代传统的 COM 类型库显示指示公共语言运行时将创建托管对象。  
  
## 请参阅  
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [如何：从 COM 中引用 .NET 类型](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/zh-cn/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/zh-cn/fb63564c-c1b9-4655-a094-a235625882ce)