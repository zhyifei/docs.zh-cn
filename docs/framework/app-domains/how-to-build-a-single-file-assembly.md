---
title: "如何：生成单文件程序集 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 单个文件"
  - "程序集清单, 单文件程序集"
  - "代码模块"
  - "命令行编译器"
  - "库程序集"
  - "程序集的输出文件名"
  - "单文件程序集"
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：生成单文件程序集
单文件程序集（最简单的程序集类型）包含类型信息和实现，以及[程序集清单](../../../docs/framework/app-domains/assembly-manifest.md)。  可以使用命令行编译器或 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 创建单文件程序集。  默认情况下，编译器创建带 .exe 扩展名的程序集文件。  
  
> [!NOTE]
>  对于 C\# 和 Visual Basic，[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 只能用于创建单文件程序集。  如果要创建多文件程序集，必须使用命令行编译器或带有 Visual C\+\+ 的 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]。  
  
 下面的步骤说明如何使用命令行编译器创建单文件程序集。  
  
### 创建带 .exe 扩展名的程序集  
  
1.  在命令提示符处，键入下列命令：  
  
     \<*compiler command*\> \<*module name*\>  
  
     在此命令中，“编译器命令”是代码模块中所用语言的编译器命令，“模块名”是要编译为程序集的代码模块的名称。  
  
 下面的示例从名为 `myCode` 的代码模块创建名为 `myCode.exe` 的程序集。  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### 创建具有 .exe 扩展名的程序集并指定输出文件名  
  
1.  在命令提示符处，键入下列命令：  
  
     \<*compiler command*\> **\/out:**\<*file name*\> \<*module name*\>  
  
     在此命令中，“编辑器命令”是用于代码模块中所用语言的编译器命令，“文件名”是输出文件名称，而“模块名”是要编译成程序集的代码模块的名称。  
  
 下面的示例从名为 `myCode` 的代码模块创建名为 `myAssembly.exe` 的程序集。  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## 创建库程序集  
 库程序集与类库相似。  它包含将由其他程序集引用的类型，但没有开始执行的入口点。  
  
#### 创建库程序集  
  
1.  在命令提示符处，键入下列命令：  
  
     \<*compiler command*\> **\/t:library** \<*module name*\>  
  
     在此命令中，“编译器命令”是代码模块中所用语言的编译器命令，“模块名”是要编译为程序集的代码模块的名称。  您也可以使用其他编译器选项，例如 **\/out:** 选项。  
  
 下面的示例从名为 `myCode` 的代码模块创建名为 `myCodeAssembly.dll` 的库程序集。  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## 请参阅  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)   
 [多文件程序集](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [如何：生成多文件程序集](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)