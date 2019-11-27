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
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="21b26-102">如何：在 Visual Basic 中使用 StringBuilder 创建字符串</span><span class="sxs-lookup"><span data-stu-id="21b26-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="21b26-103">此示例使用 <xref:System.Text.StringBuilder> 类从多个较小的字符串构造一个长字符串。</span><span class="sxs-lookup"><span data-stu-id="21b26-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="21b26-104"><xref:System.Text.StringBuilder> 类比用于连接多个字符串的 `&=` 运算符更有效。</span><span class="sxs-lookup"><span data-stu-id="21b26-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="21b26-105">示例</span><span class="sxs-lookup"><span data-stu-id="21b26-105">Example</span></span>

<span data-ttu-id="21b26-106">下面的示例创建 <xref:System.Text.StringBuilder> 类的实例，将1000字符串追加到该实例，然后返回该实例的字符串表示形式：</span><span class="sxs-lookup"><span data-stu-id="21b26-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="21b26-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21b26-107">See also</span></span>

- [<span data-ttu-id="21b26-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="21b26-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="21b26-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="21b26-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="21b26-110">字符串</span><span class="sxs-lookup"><span data-stu-id="21b26-110">Strings</span></span>](index.md)
- [<span data-ttu-id="21b26-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="21b26-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="21b26-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="21b26-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
