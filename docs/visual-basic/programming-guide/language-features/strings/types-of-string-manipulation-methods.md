---
title: "在 Visual Basic 中的字符串操作方法的类型 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c63ad0931ae2f3760576a792795b9fe0ab6a409
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="4e308-102">字符串操作方法的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e308-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="4e308-103">有多种不同的方式来分析和操作字符串。</span><span class="sxs-lookup"><span data-stu-id="4e308-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="4e308-104">一些方法属于的[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]语言中，而其他一些固有的`String`类。</span><span class="sxs-lookup"><span data-stu-id="4e308-104">Some of the methods are a part of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="4e308-105">Visual Basic 语言和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="4e308-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4e308-106">为该语言的固有函数使用方法。</span><span class="sxs-lookup"><span data-stu-id="4e308-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="4e308-107">它们可能无需限定即可在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="4e308-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="4e308-108">下面的示例演示的典型用法[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]字符串操作命令︰</span><span class="sxs-lookup"><span data-stu-id="4e308-108">The following example shows typical use of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string-manipulation command:</span></span>  
  
 <span data-ttu-id="4e308-109">[!code-vb[VbVbalrStrings #&44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e308-109">[!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="4e308-110">在此示例中，`Mid`函数对执行直接操作`aString`并将该值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="4e308-110">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="4e308-111">Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="4e308-111">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="4e308-112">共享的方法和实例方法</span><span class="sxs-lookup"><span data-stu-id="4e308-112">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="4e308-113">您还可以使用的方法的操作字符串`String`类。</span><span class="sxs-lookup"><span data-stu-id="4e308-113">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="4e308-114">有两种类型中的方法`String`:*共享*方法和*实例*方法。</span><span class="sxs-lookup"><span data-stu-id="4e308-114">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="4e308-115">共享的方法</span><span class="sxs-lookup"><span data-stu-id="4e308-115">Shared Methods</span></span>  
 <span data-ttu-id="4e308-116">共享的方法是一种方法起源于`String`类本身并不需要此类工作的实例。</span><span class="sxs-lookup"><span data-stu-id="4e308-116">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="4e308-117">这些方法可以使用的类名称限定 (`String`) 而不是与实例`String`类。</span><span class="sxs-lookup"><span data-stu-id="4e308-117">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="4e308-118">例如: </span><span class="sxs-lookup"><span data-stu-id="4e308-118">For example:</span></span>  
  
 <span data-ttu-id="4e308-119">[!code-vb[VbVbalrStrings #&45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e308-119">[!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="4e308-120">在前面的示例中，<xref:System.String.Copy%2A?displayProperty=fullName>方法是静态方法，对表达式的行为被授权者提供，并且生成将值分配给`bString`。</xref:System.String.Copy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e308-120">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=fullName> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="4e308-121">实例方法</span><span class="sxs-lookup"><span data-stu-id="4e308-121">Instance Methods</span></span>  
 <span data-ttu-id="4e308-122">实例方法，与此相反，源于的特定实例`String`并且必须具有实例名称进行限定。</span><span class="sxs-lookup"><span data-stu-id="4e308-122">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="4e308-123">例如：</span><span class="sxs-lookup"><span data-stu-id="4e308-123">For example:</span></span>  
  
 <span data-ttu-id="4e308-124">[!code-vb[VbVbalrStrings #&46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e308-124">[!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="4e308-125">在此示例中，<xref:System.String.Substring%2A?displayProperty=fullName>方法是一种方法的实例的`String`(即， `aString`)。</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e308-125">In this example, the <xref:System.String.Substring%2A?displayProperty=fullName> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="4e308-126">它对执行某项操作`aString`并将该值赋予`bString`。</span><span class="sxs-lookup"><span data-stu-id="4e308-126">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="4e308-127">有关详细信息，请参阅的文档<xref:System.String>类。</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="4e308-127">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e308-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e308-128">See Also</span></span>  
 [<span data-ttu-id="4e308-129">在 Visual Basic 中字符串的简介</span><span class="sxs-lookup"><span data-stu-id="4e308-129">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
