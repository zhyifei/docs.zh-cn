---
title: 已声明的 XML 元素和特性的名称 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07666ead0770c8055a62f75cb481648b0c72ef8b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="0155a-102">已声明的 XML 元素和特性的名称 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0155a-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="0155a-103">本主题提供 Visual Basic 准则命名 XML 元素和 XML 文本中的属性。</span><span class="sxs-lookup"><span data-stu-id="0155a-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="0155a-104">在 XML 文本，可以指定本地名称或限定的名称。</span><span class="sxs-lookup"><span data-stu-id="0155a-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="0155a-105">限定的名称由 XML 命名空间前缀、 冒号和本地名称组成。</span><span class="sxs-lookup"><span data-stu-id="0155a-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="0155a-106">有关 XML 命名空间前缀的详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="0155a-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0155a-107">规则</span><span class="sxs-lookup"><span data-stu-id="0155a-107">Rules</span></span>  
 <span data-ttu-id="0155a-108">元素或在 Visual Basic 中的属性的本地名称必须遵守以下规则。</span><span class="sxs-lookup"><span data-stu-id="0155a-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="0155a-109">它可以开始使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="0155a-109">It can begin with a namespace.</span></span> <span data-ttu-id="0155a-110">它必须以字母字符或下划线开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="0155a-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="0155a-111">它必须包含仅字母字符、 十进制数字、 下划线、 句点 （.） 和连字符 （-）。</span><span class="sxs-lookup"><span data-stu-id="0155a-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="0155a-112">它不得超过 1,024 个字符。</span><span class="sxs-lookup"><span data-stu-id="0155a-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="0155a-113">出现在名称中的冒号指示命名空间划分。</span><span class="sxs-lookup"><span data-stu-id="0155a-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="0155a-114">因此，你可以使用冒号只能用于指定特定名称的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="0155a-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="0155a-115">此外，你应遵循以下准则。</span><span class="sxs-lookup"><span data-stu-id="0155a-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="0155a-116">XML 1.0 规范保留以字符串的任何大小写变体"xml"开头的所有名称。</span><span class="sxs-lookup"><span data-stu-id="0155a-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="0155a-117">因此，不要使用这些名称用作元素和属性名称。</span><span class="sxs-lookup"><span data-stu-id="0155a-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="0155a-118">名称长度准则</span><span class="sxs-lookup"><span data-stu-id="0155a-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="0155a-119">在实践中，名称应尽可能短同时在仍然能够清楚地标识的元素的性质。</span><span class="sxs-lookup"><span data-stu-id="0155a-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="0155a-120">这可以提高代码的可读性，并减少行长度和源文件大小。</span><span class="sxs-lookup"><span data-stu-id="0155a-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="0155a-121">但是，你的名称不应为太短，它不能充分描述元素或你的代码如何使用它。</span><span class="sxs-lookup"><span data-stu-id="0155a-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="0155a-122">这是你代码的可读性很重要。</span><span class="sxs-lookup"><span data-stu-id="0155a-122">This is important for the readability of your code.</span></span> <span data-ttu-id="0155a-123">如果其他人尝试理解它，或你自己正在寻求通过它您在编写后很长时间，则相应的元素名称可以节省时间。</span><span class="sxs-lookup"><span data-stu-id="0155a-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="0155a-124">在名称中的区分大小写</span><span class="sxs-lookup"><span data-stu-id="0155a-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="0155a-125">XML 元素名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0155a-125">XML element names are case sensitive.</span></span> <span data-ttu-id="0155a-126">这意味着 Visual Basic 编译器在比较时只字母大小写不同的两个名称，将其解释为不同的名称。</span><span class="sxs-lookup"><span data-stu-id="0155a-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="0155a-127">例如，它会`ABC`和`abc`为引用不同元素。</span><span class="sxs-lookup"><span data-stu-id="0155a-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="0155a-128">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="0155a-128">XML Namespaces</span></span>  
 <span data-ttu-id="0155a-129">在创建一个 XML 元素文本时，你可以指定的元素名称的 XML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="0155a-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="0155a-130">有关详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="0155a-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0155a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="0155a-131">See Also</span></span>  
 [<span data-ttu-id="0155a-132">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="0155a-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="0155a-133">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="0155a-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
