---
title: 如何：在 Visual Basic 中使用 StringBuilder 创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032118"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="69957-102">如何：在 Visual Basic 中使用 StringBuilder 创建字符串</span><span class="sxs-lookup"><span data-stu-id="69957-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="69957-103">以下示例构造一个长字符串从使用许多较小字符串<xref:System.Text.StringBuilder>类。</span><span class="sxs-lookup"><span data-stu-id="69957-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="69957-104"><xref:System.Text.StringBuilder>类是比效率更高`&=`将许多字符串连接运算符。</span><span class="sxs-lookup"><span data-stu-id="69957-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69957-105">示例</span><span class="sxs-lookup"><span data-stu-id="69957-105">Example</span></span>  
 <span data-ttu-id="69957-106">下面的示例创建的实例<xref:System.Text.StringBuilder>类，将 1,000 字符串追加到该实例，然后返回该字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="69957-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="69957-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="69957-107">See also</span></span>

- [<span data-ttu-id="69957-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="69957-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="69957-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="69957-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="69957-110">字符串</span><span class="sxs-lookup"><span data-stu-id="69957-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="69957-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="69957-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="69957-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="69957-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
