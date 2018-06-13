---
title: 如何：在 Visual Basic 中使用 StringBuilder 创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647727"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="9b17d-102">如何：在 Visual Basic 中使用 StringBuilder 创建字符串</span><span class="sxs-lookup"><span data-stu-id="9b17d-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="9b17d-103">此示例构造从使用许多较小的字符串的长字符串<xref:System.Text.StringBuilder>类。</span><span class="sxs-lookup"><span data-stu-id="9b17d-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="9b17d-104"><xref:System.Text.StringBuilder>类是比效率更高`&=`将许多字符串连接的运算符。</span><span class="sxs-lookup"><span data-stu-id="9b17d-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b17d-105">示例</span><span class="sxs-lookup"><span data-stu-id="9b17d-105">Example</span></span>  
 <span data-ttu-id="9b17d-106">下面的示例创建的实例<xref:System.Text.StringBuilder>类，将 1,000 字符串追加到该实例，然后返回其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="9b17d-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9b17d-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b17d-107">See Also</span></span>  
 [<span data-ttu-id="9b17d-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="9b17d-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="9b17d-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="9b17d-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="9b17d-110">字符串</span><span class="sxs-lookup"><span data-stu-id="9b17d-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="9b17d-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="9b17d-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="9b17d-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="9b17d-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 <span data-ttu-id="9b17d-113">[字符串示例](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b17d-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
