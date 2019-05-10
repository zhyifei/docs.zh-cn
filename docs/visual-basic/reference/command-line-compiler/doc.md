---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: c3bff4e44ddee1c4dfb6ab366464ad54e991b595
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624280"
---
# <a name="-doc"></a><span data-ttu-id="1a75b-102">-doc</span><span class="sxs-lookup"><span data-stu-id="1a75b-102">-doc</span></span>
<span data-ttu-id="1a75b-103">将文档注释处理到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="1a75b-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a75b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a75b-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="1a75b-105">自变量</span><span class="sxs-lookup"><span data-stu-id="1a75b-105">Arguments</span></span>  
  
|<span data-ttu-id="1a75b-106">术语</span><span class="sxs-lookup"><span data-stu-id="1a75b-106">Term</span></span>|<span data-ttu-id="1a75b-107">定义</span><span class="sxs-lookup"><span data-stu-id="1a75b-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1a75b-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1a75b-108">`+` &#124; `-`</span></span>|<span data-ttu-id="1a75b-109">可选。</span><span class="sxs-lookup"><span data-stu-id="1a75b-109">Optional.</span></span> <span data-ttu-id="1a75b-110">指定 + 或仅 `-doc` 会导致编译器生成文档信息并将其置于 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="1a75b-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="1a75b-111">指定 `-` 相当于未指定 `-doc`，因此不会创建任何文档信息。</span><span class="sxs-lookup"><span data-stu-id="1a75b-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="1a75b-112">如果使用 `-doc:`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="1a75b-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="1a75b-113">指定输出 XML 文件（由编译的源代码文件中的注释填充）。</span><span class="sxs-lookup"><span data-stu-id="1a75b-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="1a75b-114">如果文件名包含空格，请用引号 (" ") 括住该名称。</span><span class="sxs-lookup"><span data-stu-id="1a75b-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a75b-115">备注</span><span class="sxs-lookup"><span data-stu-id="1a75b-115">Remarks</span></span>  
 <span data-ttu-id="1a75b-116">`-doc` 选项控制编译器是否生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1a75b-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="1a75b-117">如果使用 `-doc:file` 语法，`file` 参数会指定 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1a75b-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="1a75b-118">如果使用 `-doc` 或 `-doc+`，编译器会从其正在创建的可执行文件或库中获取 XML 文件名。</span><span class="sxs-lookup"><span data-stu-id="1a75b-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="1a75b-119">如果使用 `-doc-` 或未指定 `-doc` 选项，则编译器不会创建 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1a75b-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="1a75b-120">在源代码文件中，文档注释可先于以下定义：</span><span class="sxs-lookup"><span data-stu-id="1a75b-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="1a75b-121">用户定义类型，例如[类](../../../visual-basic/language-reference/statements/class-statement.md)或[接口](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1a75b-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="1a75b-122">成员，例如字段、[事件](../../../visual-basic/language-reference/statements/event-statement.md)、[属性](../../../visual-basic/language-reference/statements/property-statement.md)、[函数](../../../visual-basic/language-reference/statements/function-statement.md)或[子例程](../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="1a75b-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="1a75b-123">若要将生成的 XML 文件与 Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) 功能配合使用，请将 XML 文件的文件名设为与要支持的程序集相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1a75b-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="1a75b-124">确保 XML 文件与程序集位于同一目录中，以便在 Visual Studio 项目中引用此程序集时，也可以找到 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a75b-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="1a75b-125">IntelliSense 不需要 XML 文档文件来处理项目内或项目引用的项目中的代码。</span><span class="sxs-lookup"><span data-stu-id="1a75b-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="1a75b-126">除非使用 `/target:module` 进行编译，否则 XML 文件包含标记 `<assembly></assembly>`。</span><span class="sxs-lookup"><span data-stu-id="1a75b-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="1a75b-127">这些标记指定包含编译输出文件的程序集清单的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1a75b-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="1a75b-128">有关从代码中的注释生成文档的方法，请参阅 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1a75b-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="1a75b-129">在 Visual Studio 集成开发环境中设置 -doc</span><span class="sxs-lookup"><span data-stu-id="1a75b-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1a75b-130">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="1a75b-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1a75b-131">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="1a75b-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1a75b-132">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="1a75b-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1a75b-133">3.在“生成 XML 文档文件”框中设置值。</span><span class="sxs-lookup"><span data-stu-id="1a75b-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1a75b-134">示例</span><span class="sxs-lookup"><span data-stu-id="1a75b-134">Example</span></span>  
 <span data-ttu-id="1a75b-135">有关示例，请参阅[使用 XML 来记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="1a75b-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a75b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a75b-136">See also</span></span>

- [<span data-ttu-id="1a75b-137">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1a75b-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1a75b-138">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="1a75b-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
