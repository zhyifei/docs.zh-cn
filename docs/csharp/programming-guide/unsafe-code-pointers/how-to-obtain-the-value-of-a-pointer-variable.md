---
title: "如何：获取指针变量的值（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8065c10bec737789f13dcbafe147b50eedb9da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>如何：获取指针变量的值（C# 编程指南）
使用指针间接寻址运算符在指针指向的位置获取变量。 表达式采用以下形式，其中 `p` 为指针类型：  
  
```  
*p;  
```  
  
 不能对指针类型外的任何类型的表达式使用一元间接寻址运算符。 此外，不能将其应用于 [void](../../../csharp/language-reference/keywords/void.md) 指针。  
  
 将间接寻址运算符应用于 [null](../../../csharp/language-reference/keywords/null.md) 指针时，结果具体取决于实现。  
  
## <a name="example"></a>示例  
 在下面的示例中，`char` 类型的变量可通过使用另一类型的指针进行访问。 请注意，`theChar` 地址将随着每次运行有所不同，因为分配给变量的物理地址可变。  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 **值的 theChar = Z**  
theChar 的地址 = 12F718  
pChar 的值 = Z   
pInt 的值 = 90    
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [类型](../../../csharp/language-reference/keywords/types.md)  
 [不安全](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
