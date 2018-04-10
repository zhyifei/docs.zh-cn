---
title: fixed 语句（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a>fixed 语句（C# 参考）
`fixed` 语句可防止垃圾回收器重新定位可移动的变量。 `fixed` 语句仅允许存在于[不安全的](../../../csharp/language-reference/keywords/unsafe.md)上下文中。 `Fixed` 还可用于创建[固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)。  
  
 `fixed` 语句将为托管变量设置一个指针，并在该语句的执行过程中“单边锁定”该变量。 如果没有 `fixed`，指向可移动的托管变量的指针将几乎没有什么用处，因为垃圾回收可能会不可预见地重新定位变量。 C# 编译器只允许将指针分配给 `fixed` 语句中的托管变量。  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 可以通过使用一个数组、字符串、固定大小的缓冲区或变量的地址来初始化指针。 下面的示例说明了变量地址、数组和字符串的使用。 有关固定大小的缓冲区的详细信息，请参阅[固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)。  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 可以初始化多个指针，只要它们的类型相同。  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 若要初始化不同类型的指针，只需嵌套 `fixed` 语句，如下面的示例中所示。  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 执行该语句中的代码之后，任何固定的变量都将被解锁并受垃圾回收的约束。 因此，请勿指向 `fixed` 语句之外的那些变量。  
  
> [!NOTE]
>  不能修改在固定语句中初始化的指针。  
  
 在不安全模式中，可以在堆栈上分配内存，在这种情况下，内存不受垃圾回收的约束，因此不需要固定。 有关详细信息，请参阅 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [不安全](../../../csharp/language-reference/keywords/unsafe.md)  
 [固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
