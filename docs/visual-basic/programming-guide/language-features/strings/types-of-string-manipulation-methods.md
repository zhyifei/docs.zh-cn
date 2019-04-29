---
title: 字符串操作方法的类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938263"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="2dd26-102">字符串操作方法的类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dd26-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="2dd26-103">有几种不同的方法来分析和操作字符串。</span><span class="sxs-lookup"><span data-stu-id="2dd26-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="2dd26-104">某些方法是 Visual Basic 语言的一部分，而有些固有`String`类。</span><span class="sxs-lookup"><span data-stu-id="2dd26-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="2dd26-105">Visual Basic 语言和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2dd26-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="2dd26-106">Visual Basic 方法用作语言的固有功能。</span><span class="sxs-lookup"><span data-stu-id="2dd26-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="2dd26-107">他们可能使用而无需在代码中的限定。</span><span class="sxs-lookup"><span data-stu-id="2dd26-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="2dd26-108">下面的示例演示 Visual Basic 字符串操作命令的典型用法：</span><span class="sxs-lookup"><span data-stu-id="2dd26-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="2dd26-109">在此示例中，`Mid`函数对执行直接运算`aString`并将值分配给`bString`。</span><span class="sxs-lookup"><span data-stu-id="2dd26-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="2dd26-110">Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="2dd26-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="2dd26-111">共享的方法和实例方法</span><span class="sxs-lookup"><span data-stu-id="2dd26-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="2dd26-112">您还可以使用方法的操作字符串`String`类。</span><span class="sxs-lookup"><span data-stu-id="2dd26-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="2dd26-113">有两种类型的方法中`String`:*共享*方法并*实例*方法。</span><span class="sxs-lookup"><span data-stu-id="2dd26-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="2dd26-114">共享的方法</span><span class="sxs-lookup"><span data-stu-id="2dd26-114">Shared Methods</span></span>  
 <span data-ttu-id="2dd26-115">共享的方法是源于方法`String`类本身并不需要处理，该类的实例。</span><span class="sxs-lookup"><span data-stu-id="2dd26-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="2dd26-116">这些方法可使用的类名称限定 (`String`)，而非包含的实例`String`类。</span><span class="sxs-lookup"><span data-stu-id="2dd26-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="2dd26-117">例如：</span><span class="sxs-lookup"><span data-stu-id="2dd26-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="2dd26-118">在前面的示例中，<xref:System.String.Copy%2A?displayProperty=nameWithType>方法是静态方法，对表达式的行为它给出并将结果值输出到`bString`。</span><span class="sxs-lookup"><span data-stu-id="2dd26-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="2dd26-119">实例方法</span><span class="sxs-lookup"><span data-stu-id="2dd26-119">Instance Methods</span></span>  
 <span data-ttu-id="2dd26-120">实例方法，与此相反，源于的特定实例`String`，并且必须具有实例名称限定。</span><span class="sxs-lookup"><span data-stu-id="2dd26-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="2dd26-121">例如：</span><span class="sxs-lookup"><span data-stu-id="2dd26-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="2dd26-122">在此示例中，<xref:System.String.Substring%2A?displayProperty=nameWithType>方法是一种方法的实例的`String`(即， `aString`)。</span><span class="sxs-lookup"><span data-stu-id="2dd26-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="2dd26-123">它对执行操作`aString`并将该值赋予`bString`。</span><span class="sxs-lookup"><span data-stu-id="2dd26-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="2dd26-124">有关详细信息，请参阅的文档<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="2dd26-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd26-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dd26-125">See also</span></span>

- [<span data-ttu-id="2dd26-126">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="2dd26-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
