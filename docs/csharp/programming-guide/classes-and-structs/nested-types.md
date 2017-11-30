---
title: "嵌套类型（C# 编程指南）"
ms.date: 07/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>嵌套类型（C# 编程指南）
在[类](../../../csharp/language-reference/keywords/class.md)或[构造](../../../csharp/language-reference/keywords/struct.md)中定义的类型称为嵌套类型。 例如:   
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
不论外部类型是类还是构造，嵌套类型均默认为 [private](../../../csharp/language-reference/keywords/private.md)；仅可从其包含类型中进行访问。 在上一个示例中，`Nested` 类无法访问外部类型。 

还可指定[访问修饰符](../../language-reference/keywords/access-modifiers.md)来定义嵌套类型的可访问性，如下所示：

- 嵌套类型的**类**可以是[公共](../../../csharp/language-reference/keywords/public.md)，[保护](../../../csharp/language-reference/keywords/protected.md)，[内部](../../../csharp/language-reference/keywords/internal.md)，[受保护内部](../../../csharp/language-reference/keywords/protected-internal.md)，[私有](../../../csharp/language-reference/keywords/private.md)或[私有受保护](../../../csharp/language-reference/keywords/private-protected.md)。 

   但是，定义`protected`，`protected internal`或`private protected`嵌套类内的[密封类](../../language-reference/keywords/sealed.md)将生成编译器警告[CS0628](../../misc/cs0628.md)，"新的保护的成员声明为密封类中。"
  
- 构造的嵌套类型可以是 [public](../../../csharp/language-reference/keywords/public.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 [private](../../../csharp/language-reference/keywords/private.md)。
  
以下示例使 `Nested` 类为 public：
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 嵌套类型（或内部类型）可访问包含类型（或外部类型）。 若要访问包含类型，请将其作为参数传递给嵌套类型的构造函数。 例如:   
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 嵌套类型可以访问其包含类型可以访问的所有成员。 它可以访问包含类型的私有成员和受保护成员（包括所有继承的受保护成员）。  
  
 在前面的声明中，类 `Nested` 的完整名称为 `Container.Nested`。 这是用来创建嵌套类新实例的名称，如下所示：  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)
