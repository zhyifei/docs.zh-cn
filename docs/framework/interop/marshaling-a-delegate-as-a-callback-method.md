---
title: "将委托作为回调方法进行封送 | Microsoft Docs"
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
  - "数据封送处理, “回调”示例"
  - "封送处理, “回调”示例"
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 将委托作为回调方法进行封送
该示例说明如何将委托传递给需要函数指针的非托管函数。  委托是可以容纳对方法的引用的类，并且等效于类型安全函数指针或回调函数。  
  
> [!NOTE]
>  当您在调用内部使用委托时，公共语言运行时将在该调用的持续时间内防止对委托执行垃圾回收。  但是，如果非托管函数存储该委托以供在该调用完成后使用，则您必须手动防止进行垃圾回收，直到非托管函数完成对该委托的使用为止。  有关更多信息，请参见 [HandleRef 示例](http://msdn.microsoft.com/zh-cn/ab23b04e-1d53-4ec7-b27a-e892d9298959)和 [GCHandle 示例](http://msdn.microsoft.com/zh-cn/6acce798-0385-4ded-a790-77da842c113f)。  
  
 Callback 示例使用以下非托管函数（这里同时显示其原始函数声明）：  
  
-   从 PinvokeLib.dll 导出的 **TestCallBack**。  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   从 PinvokeLib.dll 导出的 **TestCallBack2**。  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/zh-cn/5d1438d7-9946-489d-8ede-6c694a08f614) 是一个自定义非托管库，它包含前面列出的函数的实现。  
  
 在该示例中，`LibWrap` 类包含 `TestCallBack` 和 `TestCallBack2` 方法的托管原型。  这两个方法都将委托作为参数传递给回调函数。  该委托的签名必须与它所引用的方法的签名相匹配。  例如，`FPtr` 和 `FPtr2` 委托的签名与 `DoSomething` 和 `DoSomething2` 方法的签名相同。  
  
## 声明原型  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## 调用函数  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## 请参阅  
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/zh-cn/a915c948-54e9-4d0f-a525-95a77fd8ed70)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/zh-cn/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)