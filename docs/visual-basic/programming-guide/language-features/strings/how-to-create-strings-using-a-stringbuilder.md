---
title: 如何：使用 StringBuilder 创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 9295b9d0cdcfdb05dfc75f75f48c16c2354b09b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344370"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>如何：在 Visual Basic 中使用 StringBuilder 创建字符串

此示例使用 <xref:System.Text.StringBuilder> 类从多个较小的字符串构造一个长字符串。 <xref:System.Text.StringBuilder> 类比用于连接多个字符串的 `&=` 运算符更有效。

## <a name="example"></a>示例

下面的示例创建 <xref:System.Text.StringBuilder> 类的实例，将1000字符串追加到该实例，然后返回该实例的字符串表示形式：

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>另请参阅

- [使用 StringBuilder 类](../../../../standard/base-types/stringbuilder.md)
- [&= 运算符](../../../language-reference/operators/and-assignment-operator.md)
- [字符串](index.md)
- [新建字符串](../../../../standard/base-types/creating-new.md)
- [控制字符串](../../../../standard/base-types/manipulating-strings.md)
