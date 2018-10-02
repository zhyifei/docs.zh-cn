---
title: 如何：使用 foreach 访问命令行自变量（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 811ee09aec7afac70f3f2c2fe5fb002232935028
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511331"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>如何：使用 foreach 访问命令行自变量（C# 编程指南）
循环访问数组的另一种方法是使用 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句，如本例所示。 `foreach` 语句可用于循环访问数组、.NET Framework 集合类或任何实现 <xref:System.Collections.IEnumerable> 接口的类或结构。  
  
> [!NOTE]
>  在 Visual Studio 中运行应用程序时，可在[“项目设计器”->“调试”页](/visualstudio/ide/reference/debug-page-project-designer)中指定命令行参数。  
  
## <a name="example"></a>示例  
 此示例演示如何使用 `foreach` 打印命令行参数。  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Array>  
- <xref:System.Collections>  
- [在命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
- [Main() 和命令行参数](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [如何：显示命令行参数](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [Main() 返回值](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
