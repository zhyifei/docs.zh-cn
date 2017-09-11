---
title: "使用 XML (Visual Basic 中) 将代码文档化 |Microsoft 文档"
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
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
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
ms.openlocfilehash: 0ce3f216f9e851feb0b3506b6ed1279b7d9479e7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="38676-102">使用 XML 将代码文档化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38676-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="38676-103">在[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，您可以记录使用 XML 将代码</span><span class="sxs-lookup"><span data-stu-id="38676-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="38676-104">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="38676-104">XML Documentation Comments</span></span>  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="38676-105">提供了一种简单的方法来自动创建项目的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="38676-105"> provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="38676-106">您可以自动生成的 XML 主干的类型和成员，，然后提供摘要、 描述性文档每个参数，并将其他备注。</span><span class="sxs-lookup"><span data-stu-id="38676-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="38676-107">与相应的安装程序，到 XML 文件与您的项目和.xml 扩展名同名自动发出 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="38676-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="38676-108">有关详细信息，请参阅[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="38676-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="38676-109">可以使用或其他操作以 XML 形式的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="38676-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="38676-110">此文件位于您的项目的输出.exe 或.dll 文件所在的目录中。</span><span class="sxs-lookup"><span data-stu-id="38676-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="38676-111">XML 文档开头`'''`。</span><span class="sxs-lookup"><span data-stu-id="38676-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="38676-112">这些注释的处理有一些限制︰</span><span class="sxs-lookup"><span data-stu-id="38676-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="38676-113">文档必须是格式正确 XML。</span><span class="sxs-lookup"><span data-stu-id="38676-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="38676-114">如果 XML 的格式不正确，则会生成警告和文档文件将包含条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="38676-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="38676-115">开发人员可以随意创建其自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="38676-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="38676-116">没有一组建议的标记 （请参见本主题中的"相关章节"）。</span><span class="sxs-lookup"><span data-stu-id="38676-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="38676-117">建议的标记的一些具有特殊含义︰</span><span class="sxs-lookup"><span data-stu-id="38676-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="38676-118">\<Param&1;> 标记用来描述的参数。</span><span class="sxs-lookup"><span data-stu-id="38676-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="38676-119">如果使用，编译器将验证该参数存在并在文档中描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="38676-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="38676-120">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="38676-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="38676-121">`cref`属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="38676-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="38676-122">编译器将验证存在此代码元素。</span><span class="sxs-lookup"><span data-stu-id="38676-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="38676-123">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="38676-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="38676-124">编译器还将考虑所有`Imports`语句在查找中描述的类型时`cref`属性。</span><span class="sxs-lookup"><span data-stu-id="38676-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="38676-125">\<摘要&1;> IntelliSense 中将使用标记[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]以显示有关类型或成员的其他信息。</span><span class="sxs-lookup"><span data-stu-id="38676-125">The \<summary> tag is used by IntelliSense in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="38676-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="38676-126">Related Sections</span></span>  
 <span data-ttu-id="38676-127">有关创建带有文档注释的 XML 文件的详细信息，请参阅以下主题︰</span><span class="sxs-lookup"><span data-stu-id="38676-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="38676-128">/doc</span><span class="sxs-lookup"><span data-stu-id="38676-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="38676-129">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="38676-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="38676-130">处理 XML 文件</span><span class="sxs-lookup"><span data-stu-id="38676-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="38676-131">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="38676-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="38676-132">Visual Studio 中的 XML 工具</span><span class="sxs-lookup"><span data-stu-id="38676-132">XML Tools in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="38676-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38676-133">See Also</span></span>  
 <span data-ttu-id="38676-134">[使用 Visual Basic 开发应用程序](../../../visual-basic/developing-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="38676-134">[Developing Applications with Visual Basic](../../../visual-basic/developing-apps/index.md) </span></span>  
<span data-ttu-id="38676-135"> [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="38676-135"> [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)</span></span>
