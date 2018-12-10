---
title: 如何：通过指针访问成员（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: b51239be8da8c45aa2d7f1ff0700884c43c07299
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130835"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>如何：通过指针访问成员（C# 编程指南）
若要访问不安全上下文中声明的结构成员，可使用成员访问运算符，如以下示例所示，其中 `p` 是包含成员 `x` 的 [struct](../../../csharp/language-reference/keywords/struct.md) 的指针。  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>示例  
 此示例中，对包含 `x` 和 `y` 两个坐标的 [struct](../../../csharp/language-reference/keywords/struct.md) `CoOrds` 进行了声明和实例化。 通过使用成员访问运算符 `->` 和实例 `home` 的指针，为 `x` 和 `y` 赋值。  
  
> [!NOTE]
>  请注意，表达式 `p->x` 等效于表达式 `(*p).x`，使用这两个表达式中任何一个获得的结果相同。  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [类型](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
