---
title: 分部（类型）（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4f57149dd18deb08aa11b72d0a6d5f71b3838bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266684"
---
# <a name="partial-type-c-reference"></a>分部（类型）（C# 参考）
通过分部类型可以定义要拆分到多个文件中的类、结构或接口。  
  
 在 File1.cs 中：  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 在 File2.cs 中，声明：  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a>备注  
 在处理大型项目或自动生成的代码（如 [Windows 窗体设计器](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)提供的代码）时，在多个文件间拆分类、结构或接口类型可能会非常有用。 分部类型可以包含[分部方法](../../../csharp/language-reference/keywords/partial-method.md)。 有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)  
 [泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)
