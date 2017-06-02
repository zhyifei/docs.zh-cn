---
title: "将类型库当作程序集导入 | Microsoft Docs"
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
  - "COM 互操作, 公开 COM 组件"
  - "COM 互操作, 导入类型库"
  - "自定义包装"
  - "向 .NET Framework 公开 COM 组件"
  - "导入类型库"
  - "与非托管代码间的互操作, 公开 COM 组件"
  - "与非托管代码间的互操作, 导入类型库"
  - "元数据"
  - "类型库"
  - "类型库导入程序"
  - "类型元数据"
  - "TypeLibConverter 类, 导入类型库作为程序集"
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 将类型库当作程序集导入
COM 类型定义通常位于类型库中。  而符合 CLS 的编译器则在程序集中生成类型元数据。  类型信息的这两种来源具有很大的区别。  本主题将说明从类型库中生成元数据的方法。  生成的程序集称为互操作程序集，其中包含的类型信息允许 .NET Framework 应用程序使用 COM 类型。  
  
 可通过两种方式将此类型信息提供给您的应用程序：  
  
-   使用仅设计时互操作程序集：从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，您可以指示编译器将互操作程序集中的类型信息嵌入到可执行文件中。  编译器只嵌入您的应用程序所使用的类型信息。  无需将互操作程序集与您的应用程序一起部署。  这是推荐采用的方法。  
  
-   部署互操作程序集：您可以创建一个对互操作程序集的标准引用。  在本例中，互操作程序集必须与您的应用程序一起部署。  如果使用此方法，且不使用专用 COM 组件，而是要将某个 COM 组件集成到托管代码中，请始终引用该组件的作者所发布的主互操作程序集 \(PIA\)。  有关生成和使用主互操作程序集的更多信息，请参见[主互操作程序集](http://msdn.microsoft.com/zh-cn/b977a8be-59a0-40a0-a806-b11ffba5c080)。  
  
 当使用仅设计时互操作程序集，您可以从 COM 组件的作者所发布的主互操作程序集中嵌入类型信息。  但是，无需将主互操作程序集与您的应用程序一起部署。  
  
 使用仅设计时互操作程序集可减少应用程序的大小，因为大多数应用程序都不会使用 COM 组件的所有功能。  编译器在嵌入类型信息时效率非常高；如果您的应用程序只使用 COM 接口的部分方法，则编译器将不会嵌入未使用的方法。  当具有嵌入的类型信息的应用程序与另一个类似的应用程序交互时，或者与使用主互操作程序集的应用程序交互时，公共语言运行时将使用类型等效规则来确定同名的两个类型是否表示相同的 COM 类型。  您无需了解这些规则即可使用 COM 对象。  不过，如果您对这些规则感兴趣，请参见[类型等效性和嵌入的互操作类型](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md)。  
  
## 生成元数据  
 COM 类型库可以是扩展名为 .tlb 的独立文件，如 Loanlib.tlb。  某些类型库嵌入在 .dll 或 .exe 文件的资源部分中。  类型库信息的其他来源包括 .olb 和 .ocx 文件。  
  
 在您找到包含目标 COM 类型的实现的类型库后，可以通过下列选项来生成包含类型元数据的互操作程序集：  
  
-   Visual Studio  
  
     Visual Studio 将类型库中的 COM 类型自动转换为程序集中的元数据。  有关说明，请参见[如何：添加对类型库的引用](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)和[演练：嵌入 Microsoft Office 程序集中的类型信息](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)。  
  
-   [类型库导入程序 \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     类型库导入程序提供命令行选项，用以调整结果 Interop 文件中的元数据、从现有类型库中导入类型以及生成互操作程序集和命名空间。  有关说明，请参见[如何：从类型库生成互操作程序集](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)。  
  
-   <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=fullName> 类  
  
     此类提供可将类型库中的 coclass 和接口转换为程序集中的元数据的方法。  此类生成与 Tlbimp.exe 相同的元数据输出。  但与 Tlbimp.exe 不同的是，<xref:System.Runtime.InteropServices.TypeLibConverter> 类可以将内存中类型库转换为元数据。  
  
-   自定义包装  
  
     当类型库不可用或不正确时，一种可选的做法是在托管源代码中创建类或接口的重复定义。  然后，用面向运行时的编译器来编译源代码以生成程序集中的元数据。  
  
     要手动定义 COM 类型，必须具备下列各项：  
  
    -   所定义的 coclass 和接口的精确描述。  
  
    -   可生成正确 .NET Framework 类定义的编译器，如 C\# 编译器。  
  
    -   有关类型库到程序集转换规则的知识。  
  
     编写自定义包装是一项高级技术。  有关如何生成自定义包装的其他信息，请参见[自定义标准包装](http://msdn.microsoft.com/zh-cn/c40d089b-6a3c-41b5-a20d-d760c215e49d)。  
  
 有关 COM 互操作导入过程的更多信息，请参见[有关从类型库转换到程序集的摘要](http://msdn.microsoft.com/zh-cn/bf3f90c5-4770-4ab8-895c-3ba1055cc958)。  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 [向 .NET Framework 公开 COM 组件](../../../docs/framework/interop/exposing-com-components.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/zh-cn/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe（类型库导入程序）](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/zh-cn/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [编译互操作项目](../../../docs/framework/interop/compiling-an-interop-project.md)   
 [部署互操作应用程序](../../../docs/framework/interop/deploying-an-interop-application.md)   
 [如何：添加对类型库的引用](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)   
 [如何：从类型库生成互操作程序集](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)   
 [演练：嵌入 Microsoft Office 程序集中的类型信息](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)