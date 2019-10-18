---
title: 使用 XML 将代码文档化 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 58c8716450fd8310b81050c86dc297c5b7527761
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524504"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="95924-102">使用 XML 将代码文档化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95924-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="95924-103">在 Visual Basic 中，可以使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="95924-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="95924-104">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="95924-104">XML Documentation Comments</span></span>

<span data-ttu-id="95924-105">Visual Basic 提供了一种简单的方法来自动创建项目的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="95924-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="95924-106">可以为类型和成员自动生成 XML 主干，然后提供每个参数的摘要、描述性文档和其他备注。</span><span class="sxs-lookup"><span data-stu-id="95924-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="95924-107">使用适当的设置，XML 文档将自动发送到与你的项目具有相同名称和 .xml 扩展名的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="95924-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="95924-108">有关详细信息，请参阅 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="95924-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="95924-109">可以使用 XML 文件或以其他方式将其作为 XML 来处理。</span><span class="sxs-lookup"><span data-stu-id="95924-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="95924-110">此文件与项目的输出 .exe 或 .dll 文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="95924-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="95924-111">XML 文档从 `'''` 开始。</span><span class="sxs-lookup"><span data-stu-id="95924-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="95924-112">处理这些注释时存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="95924-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="95924-113">文档必须是格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="95924-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="95924-114">如果 XML 格式不正确，则会生成警告，并且文档文件将会显示一条注释，指出遇到了错误。</span><span class="sxs-lookup"><span data-stu-id="95924-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="95924-115">开发人员可以随意创建自己的标记集。</span><span class="sxs-lookup"><span data-stu-id="95924-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="95924-116">建议使用一组标记（请参阅本主题中的 "相关部分"）。</span><span class="sxs-lookup"><span data-stu-id="95924-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="95924-117">部分建议标记具有特殊含义：</span><span class="sxs-lookup"><span data-stu-id="95924-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="95924-118">\<param> 标记用于描述参数。</span><span class="sxs-lookup"><span data-stu-id="95924-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="95924-119">如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。</span><span class="sxs-lookup"><span data-stu-id="95924-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="95924-120">如果验证失败，则编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="95924-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="95924-121">`cref` 属性可以附加到任何标记，以提供对代码元素的引用。</span><span class="sxs-lookup"><span data-stu-id="95924-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="95924-122">编译器验证此代码元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="95924-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="95924-123">如果验证失败，则编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="95924-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="95924-124">查找 `cref` 属性中所述的类型时，编译器还会考虑任何 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="95924-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="95924-125">Visual Studio 中的 IntelliSense 使用 \<summary > 标记来显示有关某个类型或成员的其他信息。</span><span class="sxs-lookup"><span data-stu-id="95924-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="95924-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="95924-126">Related Sections</span></span>

<span data-ttu-id="95924-127">有关创建包含文档注释的 XML 文件的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="95924-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="95924-128">-doc</span><span class="sxs-lookup"><span data-stu-id="95924-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="95924-129">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="95924-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="95924-130">处理 XML 文件</span><span class="sxs-lookup"><span data-stu-id="95924-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="95924-131">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="95924-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="95924-132">Visual Studio 中的 XML 工具</span><span class="sxs-lookup"><span data-stu-id="95924-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="95924-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="95924-133">See also</span></span>

- [<span data-ttu-id="95924-134">使用 Visual Basic 开发应用程序</span><span class="sxs-lookup"><span data-stu-id="95924-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="95924-135">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="95924-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
