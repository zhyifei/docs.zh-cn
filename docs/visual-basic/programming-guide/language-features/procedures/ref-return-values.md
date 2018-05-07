---
title: Ref 返回值 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2979359f0ffafe46a62696485bbb87b211c1704
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="support-for-reference-return-values-visual-basic"></a>引用返回值 (Visual Basic 中) 的支持

从 C# 7.0 开始，C# 语言支持*引用返回值*。 若要了解引用返回值的一种方法是它们与通过对方法的引用传递的自变量的符号相反。 通过引用传递的自变量修改时，更改变量值中反映在调用方。 当方法调用方提供的引用返回值时，由调用方对引用返回值所做的修改将反映在调用的方法的数据。

Visual Basic 不允许你到引用作者方法返回值，但它允许你使用引用返回值。 换而言之，可以调用具有引用返回值的方法，还可以修改该返回值，并为引用返回值的更改会反映在调用的方法的数据。

## <a name="modifying-the-ref-return-value-directly"></a>直接修改 ref 返回值

方法始终会成功并且没有`ByRef`参数，你可以直接修改引用返回值。 通过将新值分配给返回的引用返回值的表达式来执行此操作。 

下面的 C# 示例定义`NumericValue.IncrementValue`递增内部值并将其返回作为引用的方法返回值。 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

引用返回调用方在下面的 Visual Basic 示例然后修改值。 请注意，在行的`NumericValue.IncrementValue`方法调用不会分配给该方法的一个值。 相反，它将值分配给该方法返回的引用返回值。

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>使用一个帮助器方法

在其他情况下，直接修改方法调用的引用返回值可能不始终需要。 例如，返回的字符串的搜索方法可能无法始终找到匹配项。 在这种情况下，你想要修改的引用返回值，如果搜索成功。

下面的 C# 示例阐释了这种情况。 它定义`Sentence`用 C# 编写的类包括`FindNext`以指定的子字符串开头的句子中查找下一步的单词的方法。 该字符串作为引用返回值返回，方法引用传递的 `Boolean` 变量指示搜索是否成功。 引用返回值指示调用方可以仅读取返回的值;他或她还可以修改它，并在内部中包含的数据中反映所做的修改`Sentence`类。

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

直接修改引用返回值在这种情况下是不可靠的因为方法调用可能会失败，以查找匹配项并返回该句中的第一个单词。 在这种情况下，调用方将无意中修改句子的第一个单词。 这可能会阻止由调用方返回`null`(或`Nothing`在 Visual Basic 中)。 但在这种情况下，尝试修改一个字符串，其值`Nothing`引发<xref:System.NullReferenceException>。 如果无法设置还将阻止由调用方返回<xref:System.String.Empty?displayProperty=nameWithType>，但这要求调用方定义其值是一个字符串变量<xref:System.String.Empty?displayProperty=nameWithType>。 当调用方可以修改该字符串时，修改本身没有任何用途，因为修改后的字符串存储该句中的单词没有关系`Sentence`类。

处理这种情况的最佳方法是将引用返回值传递通过引用向一个帮助器方法。 帮助器方法然后包含逻辑，以便确定是否方法调用成功，否则，若要修改引用返回值。 下面的示例提供一个可能的实现。

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>请参阅

[通过值和通过引用传递自变量](passing-arguments-by-value-and-by-reference.md)   
[Visual Basic 中的过程](index.md)   


