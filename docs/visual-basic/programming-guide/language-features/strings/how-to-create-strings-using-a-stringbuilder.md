---
title: 如何：使用字符串生成器创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645329"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="a49bc-102">如何：在可视化基础中使用字符串生成器创建字符串</span><span class="sxs-lookup"><span data-stu-id="a49bc-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="a49bc-103">此示例使用<xref:System.Text.StringBuilder>类从许多较小的字符串构造长字符串。</span><span class="sxs-lookup"><span data-stu-id="a49bc-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="a49bc-104">类<xref:System.Text.StringBuilder>比`&=`运算符串联许多字符串更有效。</span><span class="sxs-lookup"><span data-stu-id="a49bc-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="a49bc-105">示例</span><span class="sxs-lookup"><span data-stu-id="a49bc-105">Example</span></span>

<span data-ttu-id="a49bc-106">下面的示例创建类的<xref:System.Text.StringBuilder>实例，将 1，000 个字符串追加到该实例，然后返回其字符串表示形式：</span><span class="sxs-lookup"><span data-stu-id="a49bc-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="a49bc-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a49bc-107">See also</span></span>

- [<span data-ttu-id="a49bc-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="a49bc-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="a49bc-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="a49bc-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="a49bc-110">字符串</span><span class="sxs-lookup"><span data-stu-id="a49bc-110">Strings</span></span>](index.md)
- [<span data-ttu-id="a49bc-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="a49bc-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="a49bc-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="a49bc-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
