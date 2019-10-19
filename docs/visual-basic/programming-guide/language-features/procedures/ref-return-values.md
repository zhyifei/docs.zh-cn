---
title: 引用返回值（Visual Basic）
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: 7401fdd0fa876d21a87dbe9faf9d979e6b3bdc5c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581124"
---
# <a name="support-for-reference-return-values-visual-basic"></a>支持引用返回值（Visual Basic）

从C# 7.0 开始，该C#语言支持*引用返回值*。 了解引用返回值的一种方法是，它们与通过引用传递给方法的参数相反。 当修改通过引用传递的参数时，所做的更改将反映在调用方上的变量值中。 当方法为调用方提供引用返回值时，调用方对引用返回值所做的修改会反映在被调用方法的数据中。

Visual Basic 不允许使用引用返回值创作方法，但允许使用引用返回值。 换言之，您可以调用具有引用返回值的方法并修改该返回值，对引用返回值所做的更改将反映在被调用方法的数据中。

## <a name="modifying-the-ref-return-value-directly"></a>直接修改引用返回值

对于始终成功且无 `ByRef` 参数的方法，您可以直接修改引用返回值。 为此，可将新值分配给返回引用返回值的表达式。

下面C#的示例定义了一个 `NumericValue.IncrementValue` 方法，该方法递增内部值并将其作为引用返回值返回。

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

然后，调用方在下面 Visual Basic 示例中修改引用返回值。 请注意，具有 `NumericValue.IncrementValue` 方法调用的行不会向方法分配值。 相反，它将值赋给方法返回的引用返回值。

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>使用 helper 方法

在其他情况下，可能不会始终需要直接修改方法调用的引用返回值。 例如，返回字符串的搜索方法可能并不总是找到匹配项。 在这种情况下，只需在搜索成功时才修改引用返回值。

下面C#的示例演示了这种情况。 它定义了一个使用编写的C# `Sentence` 类包含一个 `FindNext` 方法，该方法在以指定的子字符串开头的句子中查找下一个单词。 该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。 引用返回值指示调用方不能只读取返回的值;他（她）也可以对其进行修改，并且该修改会反映在 `Sentence` 类内部包含的数据中。

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

在这种情况下直接修改引用返回值是不可靠的，因为方法调用可能找不到匹配项，并返回句子中的第一个单词。 在这种情况下，调用方将无意中修改句子的第一个单词。 调用方可以通过返回 `null` （或 Visual Basic 中的 `Nothing`）来防止此情况。 但在这种情况下，尝试修改其值为 `Nothing` 的字符串将引发 <xref:System.NullReferenceException>。 如果调用方也可能会阻止 <xref:System.String.Empty?displayProperty=nameWithType>，但这要求调用方定义值为 <xref:System.String.Empty?displayProperty=nameWithType> 的字符串变量。 虽然调用方可以修改该字符串，但修改本身并没有作用，因为修改后的字符串与 `Sentence` 类存储的句子中的单词无关。

处理此方案的最佳方式是通过引用向 helper 方法传递引用返回值。 然后，帮助器方法包含用于确定方法调用是否成功的逻辑，如果是，则修改引用返回值。 下面的示例提供了一个可能的实现。

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>请参阅

- [按值和按引用传递自变量](passing-arguments-by-value-and-by-reference.md)
- [Visual Basic 中的过程](index.md)
