---
title: unsafe（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 367a080cf58514b3ffcc30c17d8fe7bb07e0e9ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="unsafe-c-reference"></a>unsafe（C# 参考）
`unsafe` 关键字表示不安全上下文，该上下文是任何涉及指针的操作所必需的。 有关详细信息，请参阅[不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)。  
  
 可在类型或成员的声明中使用 `unsafe` 修饰符。 因此，类型或成员的整个正文范围均被视为不安全上下文。 以下面使用 `unsafe` 修饰符声明的方法为例：  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 不安全上下文的范围从参数列表扩展到方法的结尾，因此也可在以下参数列表中使用指针：  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 还可以使用不安全块从而能够使用该块内的不安全代码。 例如:  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 若要编译不安全代码，必须指定 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。 不能通过公共语言运行时验证不安全代码。  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
