---
title: 使用 XML 将代码文档化 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: fa642adcfea9e80b41b5fc148df2b95b8fa44d88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650496"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="a2138-102">使用 XML 将代码文档化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2138-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="a2138-103">在 Visual Basic 中，可以记录你的代码使用 XML</span><span class="sxs-lookup"><span data-stu-id="a2138-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="a2138-104">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="a2138-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="a2138-105">Visual Basic 可以轻松地自动创建的项目的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a2138-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="a2138-106">你可以自动生成类型和成员的 XML 主干并且然后为每个参数和其他备注中提供摘要、 描述性文档。</span><span class="sxs-lookup"><span data-stu-id="a2138-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="a2138-107">借助适当的安装中，XML 文档在自动发送到具有相同名称为你的项目和.xml 扩展名的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a2138-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="a2138-108">有关详细信息，请参阅 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="a2138-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="a2138-109">可以使用或其他操作以 XML 形式的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="a2138-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="a2138-110">此文件位于与你的项目的输出.exe 或.dll 文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="a2138-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="a2138-111">XML 文档开头`'''`。</span><span class="sxs-lookup"><span data-stu-id="a2138-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="a2138-112">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="a2138-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="a2138-113">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="a2138-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="a2138-114">如果 XML 的格式不正确，会生成一个警告，并且文档文件包含条注释，指出遇到错误。</span><span class="sxs-lookup"><span data-stu-id="a2138-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="a2138-115">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="a2138-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="a2138-116">没有一套建议的标记 （请参阅本主题中的"相关章节"）。</span><span class="sxs-lookup"><span data-stu-id="a2138-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="a2138-117">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="a2138-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="a2138-118">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="a2138-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="a2138-119">如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="a2138-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="a2138-120">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="a2138-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="a2138-121">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="a2138-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="a2138-122">编译器会验证此代码元素存在。</span><span class="sxs-lookup"><span data-stu-id="a2138-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="a2138-123">如果验证失败，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="a2138-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="a2138-124">编译器还将考虑所有`Imports`语句时查找类型中所述`cref`属性。</span><span class="sxs-lookup"><span data-stu-id="a2138-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="a2138-125">\<摘要 > 标记用于通过 Visual Studio 中的 IntelliSense，以显示有关类型或成员的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a2138-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2138-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="a2138-126">Related Sections</span></span>  
 <span data-ttu-id="a2138-127">有关创建带有文档注释的 XML 文件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a2138-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a2138-128">/doc</span><span class="sxs-lookup"><span data-stu-id="a2138-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="a2138-129">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="a2138-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="a2138-130">处理 XML 文件</span><span class="sxs-lookup"><span data-stu-id="a2138-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="a2138-131">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="a2138-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="a2138-132">Visual Studio 中的 XML 工具</span><span class="sxs-lookup"><span data-stu-id="a2138-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="a2138-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2138-133">See Also</span></span>  
 [<span data-ttu-id="a2138-134">使用 Visual Basic 开发应用程序</span><span class="sxs-lookup"><span data-stu-id="a2138-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="a2138-135">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="a2138-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
