---
title: 分部类型（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47208271"
---
# <a name="partial-type-c-reference"></a>分部类型（C# 参考）

通过分部类型可以定义要拆分到多个文件中的类、结构或接口。

在 File1.cs 中：

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

在 File2.cs 中，声明：

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a>备注

在处理大型项目或自动生成的代码（如 [Windows 窗体设计器](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)提供的代码）时，在多个文件间拆分类、结构或接口类型可能会非常有用。 分部类型可以包含[分部方法](partial-method.md)。 有关详细信息，请参阅[分部类和方法](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)。

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [修饰符](modifiers.md)
- [泛型介绍](../../programming-guide/generics/introduction-to-generics.md)