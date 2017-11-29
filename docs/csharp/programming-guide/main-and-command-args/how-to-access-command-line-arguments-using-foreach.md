---
title: "如何：使用 foreach 访问命令行自变量（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 557e72342901fab8bbe66e9cc3405cb4b2d9c1e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>如何：使用 foreach 访问命令行自变量（C# 编程指南）
循环访问数组的另一种方法是使用 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句，如本例所示。 `foreach` 语句可用于循环访问数组、.NET Framework 集合类或任何实现 <xref:System.Collections.IEnumerable> 接口的类或结构。  
  
> [!NOTE]
>  在 Visual Studio 中运行应用程序时，可在[“项目设计器”->“调试”页](/visualstudio/ide/reference/debug-page-project-designer)中指定命令行参数。  
  
## <a name="example"></a>示例  
 此示例演示如何使用 `foreach` 打印命令行参数。  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Array>  
 <xref:System.Collections>  
 [在命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main() 和命令行参数](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [如何：显示命令行参数](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Main() 返回值](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
