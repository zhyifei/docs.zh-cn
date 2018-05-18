---
title: public（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: abf7219359c108108b1ce3a3fde3dc10f9a8732d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="public-c-reference"></a>public（C# 参考）
`public` 关键字是类型和类型成员的访问修饰符。 公共访问是允许的最高访问级别。 对访问公共成员没有限制，如以下示例所示：  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)和[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。  
  
## <a name="example"></a>示例  
 在下面的示例中，声明了两个类：`PointTest` 和 `MainClass`。 直接从 `MainClass` 访问 `PointTest` 的公共成员 `x` 和 `y`。  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 如果将 `public` 访问级别更改为 [private](../../../csharp/language-reference/keywords/private.md) 或 [protected](../../../csharp/language-reference/keywords/protected.md)，则会收到错误消息：  
  
 “PointTest.y”不可访问，因为它受保护级别限制。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
