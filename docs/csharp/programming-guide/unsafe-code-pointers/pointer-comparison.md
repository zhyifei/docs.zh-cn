---
title: 指针比较 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 72d9017064959c801bd2702ff585ee16b1592da6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236786"
---
# <a name="pointer-comparison-c-programming-guide"></a>指针比较（C# 编程指南）
可以应用以下运算符比较任何类型的指针：  
  
 **==   !=   \<   >   \<=   >=**  
  
 比较运算符比较两个操作数的地址，如同它们是无符号整数。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>示例输出  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)  
- [操作指针](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [类型](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
