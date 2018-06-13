---
title: 字符串操作方法的类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648689"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="c84ad-102">字符串操作方法的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c84ad-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="c84ad-103">有多种不同的方式来分析和操作字符串。</span><span class="sxs-lookup"><span data-stu-id="c84ad-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="c84ad-104">一些方法属于的 Visual Basic 语言中，而其他则中的固有`String`类。</span><span class="sxs-lookup"><span data-stu-id="c84ad-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="c84ad-105">Visual Basic 语言和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c84ad-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="c84ad-106">Visual Basic 方法用作固有函数的语言。</span><span class="sxs-lookup"><span data-stu-id="c84ad-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="c84ad-107">它们可能用于而无需在代码中的限定。</span><span class="sxs-lookup"><span data-stu-id="c84ad-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="c84ad-108">下面的示例演示 Visual Basic 字符串操作命令的典型用法：</span><span class="sxs-lookup"><span data-stu-id="c84ad-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="c84ad-109">在此示例中，`Mid`函数上执行的直接操作`aString`和将该值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="c84ad-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="c84ad-110">Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="c84ad-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="c84ad-111">共享的方法和实例方法</span><span class="sxs-lookup"><span data-stu-id="c84ad-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="c84ad-112">您还可以使用方法的操作字符串`String`类。</span><span class="sxs-lookup"><span data-stu-id="c84ad-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="c84ad-113">有两种类型中的方法的`String`:*共享*方法和*实例*方法。</span><span class="sxs-lookup"><span data-stu-id="c84ad-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="c84ad-114">共享的方法</span><span class="sxs-lookup"><span data-stu-id="c84ad-114">Shared Methods</span></span>  
 <span data-ttu-id="c84ad-115">共享的方法是起源于方法`String`类本身并不需要此类工作的实例。</span><span class="sxs-lookup"><span data-stu-id="c84ad-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="c84ad-116">这些方法可以使用的类名称限定 (`String`) 而不是与实例`String`类。</span><span class="sxs-lookup"><span data-stu-id="c84ad-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="c84ad-117">例如：</span><span class="sxs-lookup"><span data-stu-id="c84ad-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="c84ad-118">在前面的示例中，<xref:System.String.Copy%2A?displayProperty=nameWithType>方法是静态方法，对表达式的行为它给定并将该生成值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="c84ad-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="c84ad-119">实例方法</span><span class="sxs-lookup"><span data-stu-id="c84ad-119">Instance Methods</span></span>  
 <span data-ttu-id="c84ad-120">实例方法，与此相反，源于的特定实例`String`并且必须具有实例名称进行限定。</span><span class="sxs-lookup"><span data-stu-id="c84ad-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="c84ad-121">例如：</span><span class="sxs-lookup"><span data-stu-id="c84ad-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="c84ad-122">在此示例中，<xref:System.String.Substring%2A?displayProperty=nameWithType>方法是实例方法`String`(即， `aString`)。</span><span class="sxs-lookup"><span data-stu-id="c84ad-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="c84ad-123">它执行的操作上`aString`和将该值赋给`bString`。</span><span class="sxs-lookup"><span data-stu-id="c84ad-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="c84ad-124">有关详细信息，请参阅的文档<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="c84ad-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84ad-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c84ad-125">See Also</span></span>  
 [<span data-ttu-id="c84ad-126">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="c84ad-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
