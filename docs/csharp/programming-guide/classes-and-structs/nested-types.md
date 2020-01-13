---
title: 嵌套类型 - C# 编程指南
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705491"
---
# <a name="nested-types-c-programming-guide"></a>嵌套类型（C# 编程指南）
在[类](../../language-reference/keywords/class.md)或[构造](../../language-reference/keywords/struct.md)中定义的类型称为嵌套类型。 例如：  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
不论外部类型是类还是构造，嵌套类型均默认为 [private](../../language-reference/keywords/private.md)；仅可从其包含类型中进行访问。 在上一个示例中，`Nested` 类无法访问外部类型。 

还可指定[访问修饰符](../../language-reference/keywords/access-modifiers.md)来定义嵌套类型的可访问性，如下所示：

- “类”的嵌套类型可以是 [public](../../language-reference/keywords/public.md)、[protected](../../language-reference/keywords/protected.md)、[internal](../../language-reference/keywords/internal.md)、[protected internal](../../language-reference/keywords/protected-internal.md)、[private](../../language-reference/keywords/private.md) 或 [private protected](../../language-reference/keywords/private-protected.md)  。 

   但是，在[密封类](../../language-reference/keywords/sealed.md)中定义 `protected`、`protected internal` 或 `private protected` 嵌套类将产生编译器警告 [CS0628](../../misc/cs0628.md)“封闭类汇中声明了新的受保护成员”。
  
- 构造的嵌套类型可以是 [public](../../language-reference/keywords/public.md)、[internal](../../language-reference/keywords/internal.md) 或 [private](../../language-reference/keywords/private.md)  。
  
以下示例使 `Nested` 类为 public：
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 嵌套类型（或内部类型）可访问包含类型（或外部类型）。 若要访问包含类型，请将其作为参数传递给嵌套类型的构造函数。 例如：  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 嵌套类型可以访问其包含类型可以访问的所有成员。 它可以访问包含类型的私有成员和受保护成员（包括所有继承的受保护成员）。  
  
 在前面的声明中，类 `Nested` 的完整名称为 `Container.Nested`。 这是用来创建嵌套类新实例的名称，如下所示：  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [类和结构](./index.md)
- [访问修饰符](./access-modifiers.md)
- [构造函数](./constructors.md)
