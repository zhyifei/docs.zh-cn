---
title: "处理 XML 文件 (Visual Basic 中) |Microsoft 文档"
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
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
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
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="5976e-102">处理 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5976e-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="5976e-103">编译器在代码中被标记为生成文档中将生成每个构造一个 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="5976e-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="5976e-104">(有关如何标记您的代码的信息，请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)。)ID 字符串唯一标识指定的构造。</span><span class="sxs-lookup"><span data-stu-id="5976e-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="5976e-105">处理 XML 文件的程序可以使用 ID 字符串标识对应[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]元数据/反射项。</span><span class="sxs-lookup"><span data-stu-id="5976e-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="5976e-106">XML 文件不是代码的分层表示形式中;它是与每个元素生成的 ID 的平面列表。</span><span class="sxs-lookup"><span data-stu-id="5976e-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="5976e-107">在生成 ID 字符串时，编译器将遵循以下规则︰</span><span class="sxs-lookup"><span data-stu-id="5976e-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="5976e-108">在字符串中不放置任何空白。</span><span class="sxs-lookup"><span data-stu-id="5976e-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="5976e-109">ID 字符串的第一部分标识的那类成员标识，与单个字符后跟冒号。</span><span class="sxs-lookup"><span data-stu-id="5976e-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="5976e-110">使用下面的成员类型。</span><span class="sxs-lookup"><span data-stu-id="5976e-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="5976e-111">字符</span><span class="sxs-lookup"><span data-stu-id="5976e-111">Character</span></span>|<span data-ttu-id="5976e-112">描述</span><span class="sxs-lookup"><span data-stu-id="5976e-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="5976e-113">N</span><span class="sxs-lookup"><span data-stu-id="5976e-113">N</span></span>|<span data-ttu-id="5976e-114">namespace</span><span class="sxs-lookup"><span data-stu-id="5976e-114">namespace</span></span><br /><br /> <span data-ttu-id="5976e-115">无法将文档注释添加到命名空间中，但您可以使 CREF 引用到它们，在支持的情况。</span><span class="sxs-lookup"><span data-stu-id="5976e-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="5976e-116">T</span><span class="sxs-lookup"><span data-stu-id="5976e-116">T</span></span>|<span data-ttu-id="5976e-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="5976e-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="5976e-118">F</span><span class="sxs-lookup"><span data-stu-id="5976e-118">F</span></span>|<span data-ttu-id="5976e-119">字段︰`Dim`</span><span class="sxs-lookup"><span data-stu-id="5976e-119">field: `Dim`</span></span>|  
|<span data-ttu-id="5976e-120">P</span><span class="sxs-lookup"><span data-stu-id="5976e-120">P</span></span>|<span data-ttu-id="5976e-121">属性︰ `Property` （包括默认属性）</span><span class="sxs-lookup"><span data-stu-id="5976e-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="5976e-122">M</span><span class="sxs-lookup"><span data-stu-id="5976e-122">M</span></span>|<span data-ttu-id="5976e-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="5976e-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="5976e-124">E</span><span class="sxs-lookup"><span data-stu-id="5976e-124">E</span></span>|<span data-ttu-id="5976e-125">事件︰`Event`</span><span class="sxs-lookup"><span data-stu-id="5976e-125">event: `Event`</span></span>|  
|<span data-ttu-id="5976e-126">!</span><span class="sxs-lookup"><span data-stu-id="5976e-126">!</span></span>|<span data-ttu-id="5976e-127">错误字符串</span><span class="sxs-lookup"><span data-stu-id="5976e-127">error string</span></span><br /><br /> <span data-ttu-id="5976e-128">字符串的其余部分提供有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5976e-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="5976e-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将生成链接不能解决的错误信息。</span><span class="sxs-lookup"><span data-stu-id="5976e-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="5976e-130">第二部分`String`开始命名空间根处的项的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="5976e-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="5976e-131">用句点分隔的项、 其封闭类型和命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="5976e-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="5976e-132">如果项本身的名称包含句点，它们将取代通过数字符号 （#）。</span><span class="sxs-lookup"><span data-stu-id="5976e-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="5976e-133">假定没有项直接在其名称中包含数字符号。</span><span class="sxs-lookup"><span data-stu-id="5976e-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="5976e-134">例如的完全限定的名的`String`构造函数将`System.String.#ctor`。</span><span class="sxs-lookup"><span data-stu-id="5976e-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="5976e-135">对于属性和方法，如果该方法的参数括在括号中的参数列表将遵循。</span><span class="sxs-lookup"><span data-stu-id="5976e-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="5976e-136">如果不有任何参数，则没有括号。</span><span class="sxs-lookup"><span data-stu-id="5976e-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="5976e-137">参数由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="5976e-137">The arguments are separated by commas.</span></span> <span data-ttu-id="5976e-138">编码的每个参数都直接遵循如何编码中[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]签名。</span><span class="sxs-lookup"><span data-stu-id="5976e-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5976e-139">示例</span><span class="sxs-lookup"><span data-stu-id="5976e-139">Example</span></span>  
 <span data-ttu-id="5976e-140">下面的代码演示的 ID 为类的字符串，并生成它的成员。</span><span class="sxs-lookup"><span data-stu-id="5976e-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="5976e-141">[!code-vb[VbVbcnXmlDocComments #&10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5976e-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5976e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5976e-142">See Also</span></span>  
 <span data-ttu-id="5976e-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="5976e-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="5976e-144"> [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="5976e-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
