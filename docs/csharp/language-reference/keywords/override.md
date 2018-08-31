---
title: override（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: c0fdb777c4f5a64dbc92f6afe78cdb714585efe0
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752152"
---
# <a name="override-c-reference"></a>override（C# 参考）
扩展或修改继承的方法、属性、索引器或事件的抽象或虚拟实现需要 `override` 修饰符。  
  
## <a name="example"></a>示例  
 在此示例中，`Square` 类必须提供 `Area` 的重写实现，因为 `Area` 继承自抽象 `ShapesClass`：  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 `override` 方法提供从基类继承的成员的新实现。 通过 `override` 声明重写的方法称为重写基方法。 重写基方法必须具有与 `override` 方法相同的签名。 有关继承的信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。  
  
 不能重新非虚方法或静态方法。 重写基方法必须是 `virtual`、`abstract` 或 `override`。  
  
 `override` 声明不能更改 `virtual` 方法的可访问性。 `override` 方法和 `virtual` 方法必须具有相同[级别访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。  
  
 不能使用 `new`、`static` 或 `virtual` 修饰符修改 `override` 方法。  
  
 重写属性声明必须指定与继承的属性完全相同的访问修饰符、类型和名称，并且重写的属性必须是 `virtual`、`abstract` 或 `override`。  
  
 有关如何使用 `override` 关键字的详细信息，请参阅[使用 Override 和 New 关键字进行版本控制](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)和[了解何时使用 Override 和 New 关键字](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)。  
  
## <a name="example"></a>示例  
 此示例定义一个名为 `Employee` 的基类和一个名为 `SalesEmployee` 的派生类。 `SalesEmployee` 类包含一个额外字段 `salesbonus`，并且重写方法 `CalculatePay` 以将它考虑在内。  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)  
 [virtual](../../../csharp/language-reference/keywords/virtual.md)  
 [new](../../../csharp/language-reference/keywords/new.md)  
 [多态性](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
