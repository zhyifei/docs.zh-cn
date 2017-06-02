---
title: "令映像更易于调试 | Microsoft Docs"
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
  - "映像 [.NET Framework]，调试"
  - "要调试的可执行映像"
  - "调试 [.NET Framework]，可执行映像"
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 令映像更易于调试
在编译非托管代码时，可以通过设置 IDE 开关或命令行选项配置用于调试的可执行映像。  例如，可以在 Visual C\+\+ 中使用 \/**Zi** 命令行选项以要求它发出调试符号文件（文件扩展名 .pdb）。  类似地，\/**Od** 命令行选项通知编译器禁用优化。  如果这是必需的，则最终的代码运行速度更慢，但更易于调试。  
  
 当编译 .NET Framework 托管代码时，像 Visual C\+\+、Visual Basic 和 C\# 这样的编译器将其源程序编译成 Microsoft 中间语言 \(MSIL\)。  MSIL 随后恰好在执行前被实时 \(JIT\) 编译成本机代码。  与非托管代码一样，可以通过设置 IDE 开关或命令行选项配置用于调试的可执行映像。  此外，还可以采用十分类似的方式配置 JIT 编译以用于调试。  
  
 该 JIT 配置具有以下两方面特点：  
  
-   可以请求 JIT 编译器生成跟踪信息。  这使调试器能够将 MSIL 链与其机器码副本相配，并且能够跟踪存储局部变量和函数参数之处。在 .NET Framework 2.0 版中，JIT 编译器始终生成跟踪信息，因此不需要请求它。  
  
-   可以请求 JIT 编译器不优化最终的机器码。  
  
 通常，生成 MSIL 的编译器将基于您指定的 IDE 开关或命令行选项（例如 \/**Od**），相应设置这些 JIT 编译器选项。  
  
 在某些情况下，您可能应该更改 JIT 编译器的行为，以便减小它所生成机器码的调试难度。  例如，您可能应该针对零售版本或控制优化目的生成 JIT 跟踪信息。  可以通过初始化 \(.ini\) 文件实现此目的。  
  
 例如，如果您要调试的程序集名为 MyApp.exe，则您可以在 MyApp.exe 所在文件夹中创建名为 MyApp.ini 的文本文件，它包含以下三行：  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 您可以将每个选项的值设置为 0 或 1，并且任何缺少的选项默认为 0。  通过将 `GenerateTrackingInfo` 设置为 1 并将 `AllowOptimize` 设置为 0，可提供最简单的调试。  
  
> [!NOTE]
>  在 .NET Framework 2.0 版中，无论 `GenerateTrackingInfo` 的值是什么，JIT 编译器始终都会生成跟踪信息；但是，`AllowOptimize` 值仍然有效。  如果使用[Ngen.exe（本机映像生成器）](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 在不优化的情况下对本机映像进行预编译，则在执行 Ngen.exe 时，目标文件夹中必须包含具备 `AllowOptimize=0` 的 .ini 文件。  如果已经预编译了一个未优化的程序集，则必须先使用 NGen.exe **\/uninstall** 选项移除预编译的代码，之后再重新运行 Ngen.exe，以将代码预编译为优化的代码。  如果文件夹中不存在 .ini 文件，默认情况下，Ngen.exe 会将代码预编译为优化的代码。  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggableAttribute?displayProperty=fullName> 控制程序集的设置。  **DebuggableAttribute** 包括两个字段，这两个字段记录 JIT 编译器是否应优化和\/或生成跟踪信息的设置。  在 .NET Framework 2.0 版中，JIT 编译器始终生成跟踪信息。  
  
> [!NOTE]
>  对于零售版本，编译器不设置任何 **DebuggableAttribute**。  JIT 编译器的默认行为是生成性能最高、最不易于调试的机器码。  启用 JIT 跟踪将稍微降低性能，而禁用优化将大为降低性能。  
  
> [!NOTE]
>  **DebuggableAttribute** 一次应用于整个程序集，而不是该程序集内单独的模块。  因此，开发工具必须将自定义特性附加到程序集元数据标记（如果已经创建程序集），或附加到名为 **System.Runtime.CompilerServices.AssemblyAttributesGoHere** 的类。  然后，ALink 工具将这些 **DebuggableAttribute** 特性从每个模块中提升到它们将成为其组成部分的程序集中。  如果有冲突，则 ALink 操作将失败。  
  
> [!NOTE]
>  在 .NET Framework 1.0 版中，如果指定了 **\/clr** 和 **\/Zi** 编译器选项，则 Microsoft Visual C\+\+ 编译器将添加 **DebuggableAttribute**。  在 .NET Framework 1.1 版中，必须在代码中手动添加 **DebugabbleAttribute**，或者使用 **\/ASSEMBLYDEBUG** 链接器选项。  
  
## 请参阅  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [Enabling JIT\-Attach Debugging](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)   
 [Enabling Profiling](http://msdn.microsoft.com/zh-cn/3b669676-f0e0-4ebf-8674-68986dd2020d)