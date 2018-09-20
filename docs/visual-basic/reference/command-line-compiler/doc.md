---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003888"
---
# <a name="-doc"></a><span data-ttu-id="d130a-102">-doc</span><span class="sxs-lookup"><span data-stu-id="d130a-102">-doc</span></span>
<span data-ttu-id="d130a-103">将文档注释处理到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="d130a-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d130a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d130a-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d130a-105">自变量</span><span class="sxs-lookup"><span data-stu-id="d130a-105">Arguments</span></span>  
  
|<span data-ttu-id="d130a-106">术语</span><span class="sxs-lookup"><span data-stu-id="d130a-106">Term</span></span>|<span data-ttu-id="d130a-107">定义</span><span class="sxs-lookup"><span data-stu-id="d130a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d130a-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d130a-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d130a-109">可选。</span><span class="sxs-lookup"><span data-stu-id="d130a-109">Optional.</span></span> <span data-ttu-id="d130a-110">指定 +，或只是`-doc`，使编译器生成文档信息并将其放在一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d130a-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="d130a-111">指定`-`相当于不指定`-doc`，若要创建任何文档信息。</span><span class="sxs-lookup"><span data-stu-id="d130a-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="d130a-112">如果使用 `-doc:`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="d130a-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="d130a-113">指定输出 XML 文件中，填入编译源代码文件中的注释。</span><span class="sxs-lookup"><span data-stu-id="d130a-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="d130a-114">如果文件名包含空格，将名称括起来加上引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="d130a-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d130a-115">备注</span><span class="sxs-lookup"><span data-stu-id="d130a-115">Remarks</span></span>  
 <span data-ttu-id="d130a-116">`-doc`选项控制是否编译器生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d130a-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="d130a-117">如果您使用`-doc:file`语法，`file`参数指定的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d130a-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="d130a-118">如果您使用`-doc`或`-doc+`，编译器将从可执行文件或编译器正在创建的库中获取 XML 文件名称。</span><span class="sxs-lookup"><span data-stu-id="d130a-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="d130a-119">如果您使用`-doc-`，或者不指定`-doc`选项，编译器不会创建一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d130a-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="d130a-120">在源代码文件中，文档注释之前可以放置以下定义：</span><span class="sxs-lookup"><span data-stu-id="d130a-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="d130a-121">用户定义类型，如[类](../../../visual-basic/language-reference/statements/class-statement.md)或[接口](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d130a-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="d130a-122">成员，一个字段，例如[事件](../../../visual-basic/language-reference/statements/event-statement.md)，[属性](../../../visual-basic/language-reference/statements/property-statement.md)，[函数](../../../visual-basic/language-reference/statements/function-statement.md)，或者[子例程](../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d130a-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="d130a-123">若要使用 Visual Studio 使用生成的 XML 文件[IntelliSense](/visualstudio/ide/using-intellisense)功能，让你想要支持的程序集相同的 XML 文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="d130a-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="d130a-124">请确保 XML 文件与程序集相同的目录中，以便当 Visual Studio 项目中引用的程序集，也会找到.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d130a-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="d130a-125">XML 文档文件不需要的 IntelliSense 功能在项目中或在项目引用的项目中的代码。</span><span class="sxs-lookup"><span data-stu-id="d130a-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="d130a-126">除非使用进行编译`/target:module`，XML 文件包含的标记`<assembly></assembly>`。</span><span class="sxs-lookup"><span data-stu-id="d130a-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="d130a-127">这些标记指定包含编译输出文件的程序集清单的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d130a-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="d130a-128">请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)从代码中的注释生成文档的方法。</span><span class="sxs-lookup"><span data-stu-id="d130a-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="d130a-129">若要设置-文档在 Visual Studio 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="d130a-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d130a-130">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="d130a-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d130a-131">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="d130a-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d130a-132">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="d130a-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d130a-133">3.中的值设置**生成 XML 文档文件**框。</span><span class="sxs-lookup"><span data-stu-id="d130a-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d130a-134">示例</span><span class="sxs-lookup"><span data-stu-id="d130a-134">Example</span></span>  
 <span data-ttu-id="d130a-135">请参阅[使用 XML 记录您代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)有关的示例。</span><span class="sxs-lookup"><span data-stu-id="d130a-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d130a-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="d130a-136">See Also</span></span>  
 [<span data-ttu-id="d130a-137">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d130a-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d130a-138">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="d130a-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
