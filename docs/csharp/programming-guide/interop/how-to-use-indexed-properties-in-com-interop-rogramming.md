---
title: 如何：在 COM 互操作编程中使用索引属性（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0169bfa6eb3ba01a9a88c2b247ad3f78da67d59c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208817"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>如何：在 COM 互操作编程中使用索引属性（C# 编程指南）
索引属性改进了在 C# 编程中使用具有参数的 COM 属性的方式。 结合使用索引属性与 Visual C# 中的其他功能（如[命名实参和可选实参](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)、一种新类型（[动态](../../../csharp/language-reference/keywords/dynamic.md)）以及[嵌入类型信息](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)）可以增强 Microsoft Office 编程。  
  
 在早期版本的 C# 中，仅当 `get` 方法没有参数且 `set` 方法有且只有一个值参数时，方法才能作为属性访问。 但是，并非所有 COM 属性都符合上述限制。 例如，Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> 属性具有一个 `get` 访问器，它需要该范围名称的一个参数。 过去，由于无法直接访问 `Range` 属性，因此必须使用 `get_Range` 方法，如以下示例所示。  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 利用索引属性，你可以改为编写以下代码：  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  上一示例还使用了[可选实参](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)功能，以便忽略 `Type.Missing`。  
  
 与在 Visual C# 2008 及更早版本中设置 <xref:Microsoft.Office.Interop.Excel.Range> 对象的 `Value` 属性的值类似，需要两个参数。 一个为指定范围值类型的可选参数提供实参。 另一个提供 `Value` 属性的值。 下面的示例说明了这些方法。 两者都将 A1 单元格的值设置为 `Name`。
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 利用索引属性，你可以改为编写以下代码。  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 你不能创建自己的索引属性。 该功能仅支持使用现有索引属性。  
  
## <a name="example"></a>示例  
 以下代码显示完整示例。 有关如何设置访问 Office API 的项目的详细信息，请参阅[如何：使用 Visual C# 功能访问 Office 互操作对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)。  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>请参阅

- [命名参数和可选参数](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
- [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
- [使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [如何：在 Office 编程中使用命名参数和可选参数](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
- [如何：通过使用 Visual C# 功能访问 Office 互操作对象](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
- [演练：Office 编程](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
