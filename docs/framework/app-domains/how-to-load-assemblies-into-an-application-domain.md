---
title: "如何：将程序集加载到应用程序域中 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序域, 加载程序集"
  - "加载程序集"
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 如何：将程序集加载到应用程序域中
可以通过多种方式将程序集加载到应用程序域中。  推荐方式是使用 [System.Reflection.Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) 类的 `static`（在 Visual Basic 中为 `Shared`）<xref:System.Reflection.Assembly.Load%2A> 方法。  加载程序集的其他方式包括：  
  
-   [Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) 类的 <xref:System.Reflection.Assembly.LoadFrom%2A> 方法加载已给定其文件位置的程序集。  通过此方法加载程序集将使用不同的加载上下文。  
  
-   <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 和 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 方法将程序集加载到仅反射上下文中。  可以检查（但不能执行）加载到该上下文中的程序集，同时允许检查以其他平台为目标的程序集。  请参见[如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。  
  
> [!NOTE]
>  仅反射上下文是 .NET Framework 2.0 版中的新增功能。  
  
-   诸如 <xref:System.AppDomain> 类的 <xref:System.AppDomain.CreateInstance%2A> 和 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 之类的方法可以将程序集加载到应用程序域中。  
  
-   <xref:System.Type> 类的 <xref:System.Type.GetType%2A> 方法可加载程序集。  
  
-   <xref:System.AppDomain?displayProperty=fullName> 类的 <xref:System.AppDomain.Load%2A> 方法可以加载程序集，但它主要用于实现 COM 互操作性。  不应使用该方法将程序集加载到除从其调用该方法的应用程序域以外的其他应用程序域。  
  
> [!NOTE]
>  从 .NET Framework 2.0 版开始，对于版本号高于当前已加载运行时的 .NET Framework 版本，运行时将不加载由其进行编译的程序集。  这同样适用于主版本号和次版本号的组合。  
  
 可以指定在应用程序域间共享来自已加载程序集的实时 \(JIT\) 编译代码的方式。  有关更多信息，请参见[Application Domains and Assemblies](http://msdn.microsoft.com/zh-cn/433b04ae-4ba8-4849-9dbd-79194f240346)。  
  
## 示例  
 下面的代码将名为“example.exe”或“example.dll”的程序集加载到当前应用程序域中，从该程序集获取名为 `Example` 的类型，为该类型获取名为 `MethodA` 的无参数方法，然后执行该方法。  有关从所加载程序集中获取信息的完整讨论，请参见[动态加载和使用类型](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md)。  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## 请参阅  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Hosting Overview](http://msdn.microsoft.com/zh-cn/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/zh-cn/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [反射](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)   
 [如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Application Domains and Assemblies](http://msdn.microsoft.com/zh-cn/433b04ae-4ba8-4849-9dbd-79194f240346)