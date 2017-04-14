---
title: "解决程序集加载问题 | Microsoft Docs"
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
  - "程序集 [.NET Framework]，解决加载问题"
  - "应用程序域，加载程序集"
  - "解决程序集加载"
  - "程序集 [.NET Framework]，加载"
  - "应用程序域，解决程序集加载问题"
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 解决程序集加载问题
.NET Framework 为需要对程序集加载进行更多控制的应用程序提供 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件。  通过处理此事件，应用程序可从标准探测路径外将程序集加载到加载上下文中，从若干个程序集版本中选择要加载的程序集版本，发出动态程序集并返回它等。  本主题提供了用于处理 <xref:System.AppDomain.AssemblyResolve> 事件的指南。  
  
> [!NOTE]
>  若要在仅反射上下文中解决程序集加载，请改用 <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=fullName> 事件。  
  
## AssemblyResolve 事件的工作方式  
 当您为 <xref:System.AppDomain.AssemblyResolve> 事件注册处理程序时，只要运行时无法按名称绑定到程序集，即调用该处理程序。  例如，从用户代码中调用下面的方法会导致引发 <xref:System.AppDomain.AssemblyResolve> 事件：  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName> 方法重载或 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法重载，其第一个参数是表示要加载的程序集的显示名称的字符串（即 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName> 属性返回的字符串）。  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName> 方法重载或 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法重载，其第一个参数是表示要加载的程序集的 <xref:System.Reflection.AssemblyName> 对象。  
  
-   <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> 方法重载。  
  
-   在其他应用程序域中实例化对象的 <xref:System.AppDomain.CreateInstance%2A?displayProperty=fullName> 或 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName> 方法重载。  
  
### 事件处理程序执行的操作  
 <xref:System.AppDomain.AssemblyResolve> 事件的处理程序在 <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> 属性中接收要加载的程序集的显示名称。  如果处理程序无法识别程序集名称，它将返回 null（在 Visual Basic 中为 `Nothing`，在 Visual C\+\+ 中为 `nullptr`）。  
  
 如果处理程序识别程序集名称，则可以加载并返回满足请求的程序集。  下面的列表介绍一些示例方案。  
  
-   如果处理程序了解程序集版本的位置，则可以使用 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 或 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName> 方法加载程序集，并在成功后返回加载的程序集。  
  
-   如果处理程序可以访问存储为字节数组的程序集的数据库，则可以使用采用一个字节数组的 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法重载之一来加载字节数组。  
  
-   处理程序可以生成动态程序集并返回它。  
  
> [!NOTE]
>  处理程序必须将程序集加载到加载位置上下文、加载上下文中，或没有上下文。  如果处理程序使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=fullName> 或 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=fullName> 方法将程序集加载到仅反射上下文中，则引发 <xref:System.AppDomain.AssemblyResolve> 事件的加载尝试将失败。  
  
 事件处理程序负责返回合适的程序集。  处理程序可通过将 <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> 属性值传递给 <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> 构造函数来分析请求的程序集的显示名称。  从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，处理程序可以使用 <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 属性来确定当前请求是否为其他程序集的依赖项。  此信息可帮助标识将满足依赖项的程序集。  
  
 事件处理程序可以返回与请求的程序集版本不同的版本。  
  
 在大多数情况下，无论处理程序将程序集加载到哪个上下文中，处理程序返回的程序集都会出现在加载上下文中。  例如，如果处理程序使用 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 方法将程序集加载到加载位置上下文中，则当处理程序返回该程序集时，它将出现在加载上下文中。  但是，在下面的示例中，当处理程序返回程序集时，将显示程序集，但没有上下文：  
  
-   处理程序在没有上下文的情况下加载程序集。  
  
-   <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 属性不为 null。  
  
-   在没有上下文的情况下加载请求的程序集（即，由 <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> 属性返回的程序集）。  
  
 有关上下文的信息，请参见 <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=fullName> 方法重载。  
  
 可将同一程序集的多个版本加载到同一应用程序域中。  此做法会导致类型分配问题，因此不建议使用。  请参见[适用于程序集加载的最佳做法](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)。  
  
### 事件处理程序不应执行的操作  
 处理 <xref:System.AppDomain.AssemblyResolve> 事件的主要规则是不应尝试返回无法识别的程序集。  当您编写处理程序时，应知道哪些程序集可能引发该事件。  您的处理程序应为其他程序集返回 null。  
  
> [!IMPORTANT]
>  从 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 开始，会为附属程序集引发 <xref:System.AppDomain.AssemblyResolve> 事件。  如果处理程序尝试解决所有程序集加载请求，则此更改将影响为 .NET Framework 的早期版本编写的事件处理程序。  忽略其无法识别的程序集的事件处理程序不受此更改的影响：它们返回 null，并执行标准回退机制。  
  
 加载程序集时，事件处理程序不能使用任何可能导致递归引发 <xref:System.AppDomain.AssemblyResolve> 事件的 <xref:System.AppDomain.Load%2A?displayProperty=fullName> 或 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法重载，因为这会导致堆栈溢出。（请参见本主题前面提供的列表。）即使为负载请求提供异常处理，也会出现这种情况，因为在所有事件处理程序都返回之前不会引发任何异常。  因此，如果找不到 `MyAssembly`，则下面的代码会导致堆栈溢出：  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)]
 [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)]
 [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## 请参阅  
 [适用于程序集加载的最佳做法](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)