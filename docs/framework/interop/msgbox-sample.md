---
title: "MsgBox 示例 | Microsoft Docs"
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
  - "数据封送处理, MsgBox 示例"
  - "封送处理, MsgBox 示例"
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# MsgBox 示例
此示例演示如何通过值将字符串类型作为 In 参数传递以及何时使用 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>、<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 和 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> 字段。  
  
 MsgBox 示例使用以下非托管函数（这里同时显示其原始函数声明）：  
  
-   从 User32.dll 导出的 **MessageBox**。  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 在该示例中，`LibWrap` 类包含 `MsgBoxSample` 类调用的每一个非托管函数的托管原型。  托管原型方法 `MsgBox`、`MsgBox2` 和 `MsgBox3` 对于同一个非托管函数具有不同的声明。  
  
 `MsgBox2` 的声明将在消息框中产生不正确的输出，原因是被指定为 ANSI 的字符类型与按 Unicode 函数命名的入口点 `MessageBoxW` 不匹配。  `MsgBox3` 的声明将在 **EntryPoint**、**CharSet** 和 **ExactSpelling** 字段之间产生不匹配现象。  在调用时，`MsgBox3` 将引发异常。  有关字符串命名和名称封送处理的详细信息，请参见[指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)。  
  
## 声明原型  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## 调用函数  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## 请参阅  
 [封送处理字符串](../../../docs/framework/interop/marshaling-strings.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/zh-cn/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [字符串的默认封送处理](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)