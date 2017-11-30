---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2490529b951ef6e583e3bfa54afced89c823e874
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="doc"></a><span data-ttu-id="e8283-102">/doc</span><span class="sxs-lookup"><span data-stu-id="e8283-102">/doc</span></span>
<span data-ttu-id="e8283-103">将文档注释处理到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="e8283-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8283-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8283-104">Syntax</span></span>  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8283-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8283-105">Arguments</span></span>  
  
|<span data-ttu-id="e8283-106">术语</span><span class="sxs-lookup"><span data-stu-id="e8283-106">Term</span></span>|<span data-ttu-id="e8283-107">定义</span><span class="sxs-lookup"><span data-stu-id="e8283-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e8283-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e8283-108">`+` &#124; `-`</span></span>|<span data-ttu-id="e8283-109">可选。</span><span class="sxs-lookup"><span data-stu-id="e8283-109">Optional.</span></span> <span data-ttu-id="e8283-110">指定 +，或仅仅称为`/doc`，使编译器生成文档信息并将其放在 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e8283-110">Specifying +, or just `/doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="e8283-111">指定`-`等同于不指定`/doc`，不导致要创建任何文档信息。</span><span class="sxs-lookup"><span data-stu-id="e8283-111">Specifying `-` is the equivalent of not specifying `/doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="e8283-112">如果使用 `/doc:`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="e8283-112">Required if `/doc:` is used.</span></span> <span data-ttu-id="e8283-113">指定输出 XML 文件中，填入编译源代码文件中的注释。</span><span class="sxs-lookup"><span data-stu-id="e8283-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="e8283-114">如果文件名包含空格，请使用引号将名称 ("")。</span><span class="sxs-lookup"><span data-stu-id="e8283-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8283-115">备注</span><span class="sxs-lookup"><span data-stu-id="e8283-115">Remarks</span></span>  
 <span data-ttu-id="e8283-116">`/doc`选项控制是否编译器将生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e8283-116">The `/doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="e8283-117">如果你使用`/doc:``file`语法，`file`参数指定 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e8283-117">If you use the `/doc:``file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="e8283-118">如果你使用`/doc`或`/doc+`，编译器将从可执行文件或编译器正在创建的库中获取 XML 文件名称。</span><span class="sxs-lookup"><span data-stu-id="e8283-118">If you use `/doc` or `/doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="e8283-119">如果你使用`/doc-`或不指定`/doc`选项，编译器不创建 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e8283-119">If you use `/doc-` or do not specify the `/doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="e8283-120">在源代码文件中，文档注释可以在前面的以下定义：</span><span class="sxs-lookup"><span data-stu-id="e8283-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="e8283-121">用户定义类型，如[类](../../../visual-basic/language-reference/statements/class-statement.md)或[接口](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e8283-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="e8283-122">成员，例如一个字段，[事件](../../../visual-basic/language-reference/statements/event-statement.md)，[属性](../../../visual-basic/language-reference/statements/property-statement.md)，[函数](../../../visual-basic/language-reference/statements/function-statement.md)，或[子例程](../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e8283-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="e8283-123">若要使用生成的 XML 文件与[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense)功能，请让你想要支持的程序集相同的 XML 文件的文件名称。</span><span class="sxs-lookup"><span data-stu-id="e8283-123">To use the generated XML file with the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="e8283-124">请确保 XML 文件与程序集相同的目录中，以便当中引用的程序集[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]项目，.xml 文件也可以找到。</span><span class="sxs-lookup"><span data-stu-id="e8283-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="e8283-125">XML 文档文件不是必需的 IntelliSense 项目中或在项目引用的项目中的代码工作的。</span><span class="sxs-lookup"><span data-stu-id="e8283-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="e8283-126">除非使用编译`/target:module`，XML 文件包含标记`<assembly></assembly>`。</span><span class="sxs-lookup"><span data-stu-id="e8283-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="e8283-127">这些标记指定包含编译输出文件的程序集清单的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e8283-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="e8283-128">请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)从你的代码中的注释生成文档的方法。</span><span class="sxs-lookup"><span data-stu-id="e8283-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="e8283-129">在 Visual Studio 中设置 /doc 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="e8283-129">To set /doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e8283-130">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="e8283-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e8283-131">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="e8283-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e8283-132">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="e8283-132">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e8283-133">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="e8283-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e8283-134">3.设置中的值**生成 XML 文档文件**框。</span><span class="sxs-lookup"><span data-stu-id="e8283-134">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8283-135">示例</span><span class="sxs-lookup"><span data-stu-id="e8283-135">Example</span></span>  
 <span data-ttu-id="e8283-136">请参阅[使用 XML 编制文档您代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)有关的示例。</span><span class="sxs-lookup"><span data-stu-id="e8283-136">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8283-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8283-137">See Also</span></span>  
 [<span data-ttu-id="e8283-138">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e8283-138">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e8283-139">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="e8283-139">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
