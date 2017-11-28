---
title: "如何：递增和递减指针（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c8efc6d0844d867ad6eebccf3bb22c03e6d5020
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>如何：递增和递减指针（C# 编程指南）
使用增量运算符 (`++`) 和减量运算符 (`--`)，通过 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) 更改 pointer-type* 类型的指针的指针位置。 增量和减量表达式的形式如下：  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 增量和减量运算符可应用于除 `void*` 类型以外的任何类型的指针。  
  
 对 `pointer-type` 类型的指针应用增量运算符的效果是向指针变量中包含的地址增加 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)。  
  
 对 `pointer-type` 类型的指针应用减量运算符的效果是从指针变量中包含的地址减去 `sizeof` (`pointer-type`)。  
  
 运算溢出指针范围时，不会产生异常，并且结果取决于实现。  
  
## <a name="example"></a>示例  
 在此示例中，通过按 `int` 大小递增指针单步调试数组。 每一步都将显示数组元素的地址和内容。  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 Value:0 @ Address:12860272  
Value:1 @ Address:12860276  
Value:2 @ Address:12860280  
Value:3 @ Address:12860284  
Value:4 @ Address:12860288   
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)  
 [操作指针](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [类型](../../../csharp/language-reference/keywords/types.md)  
 [不安全](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
