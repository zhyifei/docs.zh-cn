---
title: "如何：获取变量的地址（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>如何：获取变量的地址（C# 编程指南）
若要获取计算结果为固定变量的一元表达式的地址，请使用 address-of 运算符：  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 address-of 运算符只适用于变量。 如果变量是可移动变量，则可以使用[固定语句](../../../csharp/language-reference/keywords/fixed-statement.md)临时固定变量，再获取其地址。  
  
 由你负责确保变量已初始化。 如果未初始化变量，编译器不会发出错误消息。  
  
 你也无法获取常量或值的地址。  
  
## <a name="example"></a>示例  
 在此示例中，已声明一个指向 `int` 和 `p` 的指针，并向其赋予了整型变量 `number` 的地址。 向 *p 赋值后导致初始化变量 `number`。 如果将此赋值语句作为注释，将删除变量 `number` 的初始化，但不会产生任何编译时错误。 注意使用[成员访问](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md)运算符 `->` 获取并显示指针中存储的地址。  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [类型](../../../csharp/language-reference/keywords/types.md)  
 [不安全](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
