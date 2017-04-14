---
title: "Performance Counters and In-Process Side-By-Side Applications | Microsoft Docs"
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
  - "performance counters"
  - "performance counters,and in-process side-by-side applications"
  - "performance,.NET Framework applications"
  - "performance monitoring,counters"
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Performance Counters and In-Process Side-By-Side Applications
通过使用性能监视器 \(Perfmon.exe\)，可以基于每个运行时区分性能计数器。  本主题介绍启用此功能所需的注册表更改。  
  
## 默认行为  
 默认情况下，性能监视器将基于每个应用程序显示性能计数器。  但是，这样做在以下两种情形中会出现问题：  
  
-   当监视两个名称相同的应用程序时。  例如，如果两个应用程序的名称都为 myapp.exe，二者在**“实例”**列中分别显示为**“myapp”**和**“myapp\#1”**。  在此情况下，很难将性能计数器与特定的应用程序相匹配。  无法确定为**“myapp\#1”**收集的数据是针对第一个 myapp.exe 的，还是针对第二个 myapp.exe 的。  
  
-   当应用程序使用公共语言运行时的多个实例时。  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]支持进程内并行承载方案；也就是说，一个进程或应用程序可以加载公共语言运行时的多个实例。  如果一个名为 myapp.exe 的应用程序加载两个运行时实例，则默认情况下会在**“实例”**列中将这两个实例分别指定为**“myapp”**和**“myapp\#1”**。  在此情况下，无法确定**“myapp”**和**“myapp\#1”**是指两个名称相同的应用程序，还是指带有两个运行时的同一应用程序。  如果名称相同的多个应用程序加载多个运行时，则不确定性甚至会更大。  
  
 可以设置注册表项来消除此不确定性。  对于使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 开发的应用程序，此注册表更改会向**“实例”**列中的应用程序名添加一个进程标识符，并在其后面跟一个运行时实例标识符。  应用程序将会在**Instance** column列标识被为 *application*\_`p`*processID*\_`r`*runtimeID*，而不是 *application* 或 *application*\#1 。  如果应用程序是使用早期版本的公共语言运行时开发的，则该实例将表示为 *application\_*`p`*processID*，前提是安装了 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]。  
  
## 进程内并行应用程序的性能计数器  
 若要处理单个应用程序中承载的多个公共语言运行时版本的性能计数器，则必须更改一个注册表项设置，如下表所示。  
  
|||  
|-|-|  
|项名称|HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\.NETFramework\\Performance|  
|值名称|ProcessNameFormat|  
|值类型|REG\_DWORD|  
|值|1 \(0x00000001\)|  
  
 `ProcessNameFormat` 的值为 0 指示启用默认行为，即，Perfmon.exe 将为每个应用程序显示一个性能计数器。  当将此值设为 1 时，Perfmon.exe 将消除应用程序多个版本之间的歧义，并为每个运行时提供一个性能计数器。  `ProcessNameFormat` 注册项设置的任何其他值都是不受支持的，这些值已保留以供将来使用。  
  
 在您更新 `ProcessNameFormat` 注册项设置之后，必须重新启动 Perfmon.exe 或任何其他性能计数器的使用者，以便新的实例命名功能可以正常工作。  
  
 下面的示例演示如何以编程方式更改 `ProcessNameFormat` 值。  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 在进行此注册表更改时，Perfmon.exe 会将针对[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]显示为 *application*\_`p`*processID*\_`r`*runtimeID*的应用程序的名字，其中，*application*为应用程序的名称， *processID* 应用程序的进程标识符，而 *runtimeID* 为公共语言运行时标识符。  例如，如果一个名为 myapp.exe 的应用程序加载公共语言运行时的两个实例，则 Perfmon.exe 可能会将这两个实例分别标识为 myapp\_p1416\_r10 和 myapp\_p3160\_r10。  运行时标识符仅可消除进程内的运行时之间的歧义；它不会提供有关运行时的任何其他信息。（例如，运行时 ID 与运行时的版本或 SKU 无关。）  
  
 如果安装了 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，则注册表更改还会影响使用早期版本的 .NET Framework 开发的应用程序。  这些应用程序在 Perfmon.exe 中显示为 *application\_*`p`*processID*，其中，*application* 为应用程序名称，*processID* 为进程标识符。  例如，如果对名为 myapp.exe 的两个应用程序的性能计数器进行监控，则二者可能分别显示为 myapp\_p23900 和 myapp\_p24908。  
  
> [!NOTE]
>  进程标识符可消除在解析使用早期版本的运行时的、名称相同的两个应用程序时的歧义。  由于早期版本的公共语言运行时不支持并行方案，因此它们不需要运行时标识符。  
  
 如果 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 不存在或已卸载，则设置注册表项不起任何作用。  这意味着，名称相同的两个应用程序在 Perfmon.exe 中将继续显示为*application*和*application\#1*（例如，显示为**myapp** 和**myapp\#1**）。