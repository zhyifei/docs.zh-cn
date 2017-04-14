---
title: "创建用于容纳 DLL 函数的类 | Microsoft Docs"
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
  - "COM 互操作, DLL 函数"
  - "COM 互操作, 平台调用"
  - "DLL 函数"
  - "与非托管代码间的互操作, DLL 函数"
  - "与非托管代码间的互操作, 平台调用"
  - "平台调用, 为函数创建类"
  - "非托管函数"
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 创建用于容纳 DLL 函数的类
要封装平台功能，一种有效的方法是将常用的 DLL 函数包装在托管类中。  虽然不必在每种情形下都这样做，但由于定义 DLL 函数可能会相当麻烦并且容易出错，所以提供类包装是一种很方便的方法。  如果您使用 Visual Basic 或 C\# 进行编程，则必须在一个类或 Visual Basic 模块中声明 DLL 函数。  
  
 在一个类中，为每个要调用的 DLL 函数定义静态方法。  定义中可以包括一些附加信息，如在传递方法参数时使用的字符集或调用约定；如果省略这些信息，将选择默认设置。  有关声明选项及其默认设置的完整列表，请参见[在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)。  
  
 包装之后，就可以按照对其他任何静态函数调用方法的相同方式来对该函数调用方法。  平台调用将自动处理底层的导出函数。  
  
 为平台调用设计托管类时，应考虑类和 DLL 函数之间的关系。  例如，您可以：  
  
-   在现有类内声明 DLL 函数。  
  
-   分别为每个 DLL 函数创建一个类，以便使函数相互隔离，易于查找。  
  
-   为一组相关的 DLL 函数创建一个类，以形成逻辑分组并减少系统开销。  
  
 您可以将该类及其方法命名为任意名称。  有关说明如何构造用于平台调用的基于 .NET 的声明的示例，请参见[用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)。  
  
## 请参阅  
 [使用非托管 DLL 函数](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [标识 DLL 中的函数](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [调用 DLL 函数](../../../docs/framework/interop/calling-a-dll-function.md)