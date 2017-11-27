---
title: "字符串操作方法的类型 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="4b52b-102">字符串操作方法的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b52b-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="4b52b-103">有多种不同的方式来分析和操作字符串。</span><span class="sxs-lookup"><span data-stu-id="4b52b-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="4b52b-104">一些方法属于的[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]语言和其他是所固有的`String`类。</span><span class="sxs-lookup"><span data-stu-id="4b52b-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="4b52b-105">Visual Basic 语言和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b52b-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="4b52b-106">方法用于为固有函数的语言。</span><span class="sxs-lookup"><span data-stu-id="4b52b-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="4b52b-107">它们可能用于而无需在代码中的限定。</span><span class="sxs-lookup"><span data-stu-id="4b52b-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="4b52b-108">下面的示例演示的典型用法[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符串操作命令：</span><span class="sxs-lookup"><span data-stu-id="4b52b-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="4b52b-109">在此示例中，`Mid`函数上执行的直接操作`aString`和将该值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="4b52b-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="4b52b-110">Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="4b52b-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="4b52b-111">共享的方法和实例方法</span><span class="sxs-lookup"><span data-stu-id="4b52b-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="4b52b-112">您还可以使用方法的操作字符串`String`类。</span><span class="sxs-lookup"><span data-stu-id="4b52b-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="4b52b-113">有两种类型中的方法的`String`:*共享*方法和*实例*方法。</span><span class="sxs-lookup"><span data-stu-id="4b52b-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="4b52b-114">共享的方法</span><span class="sxs-lookup"><span data-stu-id="4b52b-114">Shared Methods</span></span>  
 <span data-ttu-id="4b52b-115">共享的方法是起源于方法`String`类本身并不需要此类工作的实例。</span><span class="sxs-lookup"><span data-stu-id="4b52b-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="4b52b-116">这些方法可以使用的类名称限定 (`String`) 而不是与实例`String`类。</span><span class="sxs-lookup"><span data-stu-id="4b52b-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="4b52b-117">例如: </span><span class="sxs-lookup"><span data-stu-id="4b52b-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="4b52b-118">在前面的示例中，<xref:System.String.Copy%2A?displayProperty=nameWithType>方法是静态方法，对表达式的行为它给定并将该生成值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="4b52b-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="4b52b-119">实例方法</span><span class="sxs-lookup"><span data-stu-id="4b52b-119">Instance Methods</span></span>  
 <span data-ttu-id="4b52b-120">实例方法，与此相反，源于的特定实例`String`并且必须具有实例名称进行限定。</span><span class="sxs-lookup"><span data-stu-id="4b52b-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="4b52b-121">例如: </span><span class="sxs-lookup"><span data-stu-id="4b52b-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="4b52b-122">在此示例中，<xref:System.String.Substring%2A?displayProperty=nameWithType>方法是实例方法`String`(即， `aString`)。</span><span class="sxs-lookup"><span data-stu-id="4b52b-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="4b52b-123">它执行的操作上`aString`和将该值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="4b52b-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="4b52b-124">有关详细信息，请参阅的文档<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="4b52b-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b52b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b52b-125">See Also</span></span>  
 [<span data-ttu-id="4b52b-126">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="4b52b-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
