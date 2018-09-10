---
title: volatile（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526214"
---
# <a name="volatile-c-reference"></a>volatile（C# 参考）
`volatile` 关键字指示一个字段可以由多个同时执行的线程修改。 声明为 `volatile` 的字段不受编译器优化（假定由单个线程访问）的限制。 这些限制确保所有线程观察易失性写入操作（由任何其他线程执行）时的观察顺序与写入操作的执行顺序一致。 不确保从所有执行线程整体来看时所有易失性写入操作均按执行顺序排序。  
  
 `volatile` 修饰符通常用于由多个线程访问、但不使用 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 语句对访问进行序列化的字段。  
  
 `volatile` 关键字可应用于以下类型的字段：  
  
-   引用类型。  
  
-   指针类型（在不安全的上下文中）。 请注意，虽然指针本身可以是可变的，但是它指向的对象不能是可变的。 换句话说，不能声明“指向可变对象的指针”。  
  
-   类型，如 sbyte、byte、short、ushort、int、uint、char、float 和 bool。  
  
-   具有以下基类型之一的枚举类型：byte、sbyte、short、ushort、int 或 uint。  
  
-   已知为引用类型的泛型类型参数。  
  
-   <xref:System.IntPtr> 和 <xref:System.UIntPtr>。  
  
 可变关键字仅可应用于类或结构的字段。 不能将局部变量声明为 `volatile`。  
  
## <a name="example"></a>示例  
 下面的示例说明如何将公共字段变量声明为 `volatile`。  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建辅助线程，并用它与主线程并行执行处理。 有关多线程处理的背景信息，请参阅[托管线程](../../../standard/threading/index.md)和[线程 (C#)](../../programming-guide/concepts/threading/index.md)。  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
- [修饰符](../../../csharp/language-reference/keywords/modifiers.md)
