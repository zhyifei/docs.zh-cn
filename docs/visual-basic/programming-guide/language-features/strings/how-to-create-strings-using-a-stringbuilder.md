---
title: 如何：在 Visual Basic 中使用 StringBuilder 创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700109"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="e61c1-102">如何：在 Visual Basic 中使用 StringBuilder 创建字符串</span><span class="sxs-lookup"><span data-stu-id="e61c1-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="e61c1-103">此示例使用 <xref:System.Text.StringBuilder> 类从多个较小的字符串构造一个长字符串。</span><span class="sxs-lookup"><span data-stu-id="e61c1-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="e61c1-104">@No__t-0 类比用于串联多个字符串的 @no__t 1 运算符更有效。</span><span class="sxs-lookup"><span data-stu-id="e61c1-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="e61c1-105">示例</span><span class="sxs-lookup"><span data-stu-id="e61c1-105">Example</span></span>

<span data-ttu-id="e61c1-106">下面的示例创建一个 @no__t 为0的类的实例，将1000字符串追加到该实例，然后返回该实例的字符串表示形式：</span><span class="sxs-lookup"><span data-stu-id="e61c1-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="e61c1-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e61c1-107">See also</span></span>

- [<span data-ttu-id="e61c1-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="e61c1-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="e61c1-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="e61c1-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="e61c1-110">字符串</span><span class="sxs-lookup"><span data-stu-id="e61c1-110">Strings</span></span>](index.md)
- [<span data-ttu-id="e61c1-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="e61c1-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="e61c1-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="e61c1-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
