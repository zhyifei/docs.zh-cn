---
title: Checked 和 Unchecked（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 26ea8a7864d93b8d64661db2b0dc1df6634f989a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="checked-and-unchecked-c-reference"></a>Checked 和 Unchecked（C# 参考）
C# 语句既可以在已检查的上下文中执行，也可以在未检查的上下文中执行。 在已检查的上下文中，算法溢出引发异常。 在未检查的上下文中，算法溢出被忽略并且结果被截断。  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) 指定已检查的上下文。  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 指定未检查的上下文。  
  
 如果既未指定 `unchecked``checked` 也未指定 ，则默认上下文取决于外部因素（如编译器选项）。  
  
 下列操作受溢出检查的影响：  
  
-   表达式在整型上使用下列预定义运算符：  
  
     `++` `--` - (unary)   `+` -   `*` `/`  
  
-   整型间的显式数字转换。  
  
 使用 [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) 编译器选项，可以为非明确位于 `checked` 或 `unchecked` 关键字范围内的所有整型算术语句指定已检查或未检查的上下文。  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [语句关键字](../../../csharp/language-reference/keywords/statement-keywords.md)
