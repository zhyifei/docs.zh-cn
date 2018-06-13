---
title: break（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 0cfe722bfefc1befd8a453f4454b05b3e4a0da76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215045"
---
# <a name="break-c-reference"></a>break（C# 参考）
`break` 语句将终止其所在位置的最接近封闭循环或 [switch](../../../csharp/language-reference/keywords/switch.md) 语句。 控制权将传递给已终止语句后面的语句（若有）。  
  
## <a name="example"></a>示例  
 在此示例中，条件语句包含一个应从 1 计数到 100 的计数器；但 `break` 语句在计数器计数到 4 后终止了循环。  
  
 [!code-csharp[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]  
  
## <a name="example"></a>示例  
 在此示例中，`break` 语句用于中断内层嵌套循环，并将控制权返回给外层循环。  
  
 [!code-csharp[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]  
  
## <a name="example"></a>示例  
 本示例演示 `break` 在 [switch](../../../csharp/language-reference/keywords/switch.md) 语句中的用法。  
  
 [!code-csharp[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]  
  
 如果输入 `4`，则输出为：  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [switch](../../../csharp/language-reference/keywords/switch.md)  
 [跳转语句](../../../csharp/language-reference/keywords/jump-statements.md)  
 [迭代语句](../../../csharp/language-reference/keywords/iteration-statements.md)
