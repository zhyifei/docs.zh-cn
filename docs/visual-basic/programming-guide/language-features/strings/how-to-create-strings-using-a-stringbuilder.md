---
title: "如何：在 Visual Basic 中使用 StringBuilder 创建字符串"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="4cab2-102">如何：在 Visual Basic 中使用 StringBuilder 创建字符串</span><span class="sxs-lookup"><span data-stu-id="4cab2-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="4cab2-103">此示例构造从使用许多较小的字符串的长字符串<xref:System.Text.StringBuilder>类。</span><span class="sxs-lookup"><span data-stu-id="4cab2-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="4cab2-104"><xref:System.Text.StringBuilder>类是比效率更高`&=`将许多字符串连接的运算符。</span><span class="sxs-lookup"><span data-stu-id="4cab2-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cab2-105">示例</span><span class="sxs-lookup"><span data-stu-id="4cab2-105">Example</span></span>  
 <span data-ttu-id="4cab2-106">下面的示例创建的实例<xref:System.Text.StringBuilder>类，将 1,000 字符串追加到该实例，然后返回其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="4cab2-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4cab2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cab2-107">See Also</span></span>  
 [<span data-ttu-id="4cab2-108">使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="4cab2-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)  
 [<span data-ttu-id="4cab2-109">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="4cab2-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="4cab2-110">字符串</span><span class="sxs-lookup"><span data-stu-id="4cab2-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="4cab2-111">新建字符串</span><span class="sxs-lookup"><span data-stu-id="4cab2-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="4cab2-112">控制字符串</span><span class="sxs-lookup"><span data-stu-id="4cab2-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 [<span data-ttu-id="4cab2-113">字符串示例</span><span class="sxs-lookup"><span data-stu-id="4cab2-113">Strings Sample</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
