---
title: "XSLT 编译器 (xsltc.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b4ede7bdb8dad65e9cd959dfaa2f8956a877762
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-compiler-xsltcexe"></a><span data-ttu-id="2ae70-102">XSLT 编译器 (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="2ae70-102">XSLT Compiler (xsltc.exe)</span></span>
<span data-ttu-id="2ae70-103">XSLT 编译器 (xsltc.exe) 编译 XSLT 样式表并生成一个程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="2ae70-104">然后可以将已编译的样式表直接传递到 <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> 方法中。</span><span class="sxs-lookup"><span data-stu-id="2ae70-104">The compiled style sheet can then be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2ae70-105">不能用 xsltc.exe 生成签名的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-105">You cannot generate signed assemblies with xsltc.exe.</span></span>  
  
 <span data-ttu-id="2ae70-106">xsltc.exe 工具包含在 Visual Studio 2008 中。</span><span class="sxs-lookup"><span data-stu-id="2ae70-106">The xsltc.exe tool is included with Visual Studio 2008.</span></span> <span data-ttu-id="2ae70-107">有关详细信息，请参阅[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463)。</span><span class="sxs-lookup"><span data-stu-id="2ae70-107">For more information, see the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae70-108">语法</span><span class="sxs-lookup"><span data-stu-id="2ae70-108">Syntax</span></span>  
  
```  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a><span data-ttu-id="2ae70-109">参数</span><span class="sxs-lookup"><span data-stu-id="2ae70-109">Argument</span></span>  
  
|<span data-ttu-id="2ae70-110">参数</span><span class="sxs-lookup"><span data-stu-id="2ae70-110">Argument</span></span>|<span data-ttu-id="2ae70-111">描述</span><span class="sxs-lookup"><span data-stu-id="2ae70-111">Description</span></span>|  
|--------------|-----------------|  
|`sourceFile`|<span data-ttu-id="2ae70-112">指定样式表的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-112">Specifies the name of the style sheet.</span></span> <span data-ttu-id="2ae70-113">样式表必须是本地文件或者位于 Intranet 上。</span><span class="sxs-lookup"><span data-stu-id="2ae70-113">The style sheet must be a local file or be located on the intranet.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="2ae70-114">选项</span><span class="sxs-lookup"><span data-stu-id="2ae70-114">Options</span></span>  
  
|<span data-ttu-id="2ae70-115">选项</span><span class="sxs-lookup"><span data-stu-id="2ae70-115">Option</span></span>|<span data-ttu-id="2ae70-116">描述</span><span class="sxs-lookup"><span data-stu-id="2ae70-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2ae70-117">`/c[lass]:` `name`</span><span class="sxs-lookup"><span data-stu-id="2ae70-117">`/c[lass]:` `name`</span></span>|<span data-ttu-id="2ae70-118">指定下面样式表的类名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-118">Specifies the name of the class for the following style sheet.</span></span> <span data-ttu-id="2ae70-119">类名称可以是完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-119">The class name can be fully qualified.</span></span><br /><br /> <span data-ttu-id="2ae70-120">类名称默认为样式表的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-120">The class name defaults to the name of the style sheet.</span></span> <span data-ttu-id="2ae70-121">例如，如果编译样式表 customers.xsl，则默认类名称为 customers。</span><span class="sxs-lookup"><span data-stu-id="2ae70-121">For example, if the style sheet customers.xsl is compiled, the default class name is customers.</span></span>|  
|<span data-ttu-id="2ae70-122">`/debug[`+&#124;-`]`</span><span class="sxs-lookup"><span data-stu-id="2ae70-122">`/debug[`+&#124;-`]`</span></span>|<span data-ttu-id="2ae70-123">指定是否生成调试信息。</span><span class="sxs-lookup"><span data-stu-id="2ae70-123">Specifies whether to generate debugging information.</span></span><br /><br /> <span data-ttu-id="2ae70-124">指定 `+` 或 `/debug` 将导致编译器生成调试信息并将此信息放在程序数据库 (PDB) 文件中。</span><span class="sxs-lookup"><span data-stu-id="2ae70-124">Specifying `+` or `/debug`, causes the compiler to generate debugging information and put it in a program database (PDB) file.</span></span> <span data-ttu-id="2ae70-125">生成的 PDB 文件的名称为 `assemblyName`.pdb。</span><span class="sxs-lookup"><span data-stu-id="2ae70-125">The name of the generated PDB file is `assemblyName`.pdb.</span></span><br /><br /> <span data-ttu-id="2ae70-126">指定 `-`（在不指定 `/debug` 时生效）将导致不创建任何调试信息。</span><span class="sxs-lookup"><span data-stu-id="2ae70-126">Specifying `-`, which is in effect if you do not specify `/debug`, causes no debug information to be created.</span></span> <span data-ttu-id="2ae70-127">生成发布程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-127">A retail assembly is generated.</span></span> <span data-ttu-id="2ae70-128">**注意：**在调试模式下的编译会显著影响 XSLT 性能。</span><span class="sxs-lookup"><span data-stu-id="2ae70-128">**Note:**  Compiling in debug mode can affect XSLT performance significantly.</span></span>|  
|`/help`|<span data-ttu-id="2ae70-129">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="2ae70-129">Displays command syntax and options for the tool.</span></span>|  
|`/nologo`|<span data-ttu-id="2ae70-130">禁止显示编译器版权消息。</span><span class="sxs-lookup"><span data-stu-id="2ae70-130">Suppresses the compiler copyright message from displaying.</span></span>|  
|<span data-ttu-id="2ae70-131">`/platform:` `string`</span><span class="sxs-lookup"><span data-stu-id="2ae70-131">`/platform:` `string`</span></span>|<span data-ttu-id="2ae70-132">指定程序集可以在其上运行的平台。</span><span class="sxs-lookup"><span data-stu-id="2ae70-132">Specifies the platforms that the assembly can be run on.</span></span> <span data-ttu-id="2ae70-133">下面说明有效的平台值：</span><span class="sxs-lookup"><span data-stu-id="2ae70-133">The following describes the valid platform values:</span></span><br /><br /> <span data-ttu-id="2ae70-134">`x86` 将程序集编译成可由 32 位、x86 兼容的公共语言运行库运行</span><span class="sxs-lookup"><span data-stu-id="2ae70-134">`x86` compiles your assembly to be run by the 32-bit, x86-compatible common language runtime</span></span><br /><br /> <span data-ttu-id="2ae70-135">`x64` 将程序集编译成可由 64 位公共语言运行库在支持 AMD64 或 EM64T 指令集的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="2ae70-135">`x64` compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span><br /><br /> [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)]<span data-ttu-id="2ae70-136"> 将程序集编译成可由 64 位公共语言运行库在具有 [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] 处理器的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="2ae70-136"> compiles your assembly to be run by the 64-bit common language runtime on a computer that has an [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] processor.</span></span><br /><br /> <span data-ttu-id="2ae70-137">`anycpu` 将程序集编译成可在任何平台上运行。</span><span class="sxs-lookup"><span data-stu-id="2ae70-137">`anycpu` compiles your assembly to run on any platform.</span></span> <span data-ttu-id="2ae70-138">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2ae70-138">This is the default.</span></span>|  
|<span data-ttu-id="2ae70-139">`/out:` `assemblyName`</span><span class="sxs-lookup"><span data-stu-id="2ae70-139">`/out:` `assemblyName`</span></span>|<span data-ttu-id="2ae70-140">指定输出的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-140">Specifies the name of the assembly that is output.</span></span> <span data-ttu-id="2ae70-141">程序集名称默认为主样式表的名称；如果有多个样式表，则为第一个样式表的名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-141">The assembly name defaults to the name of the main style sheet or the first style sheet if multiple style sheets are present.</span></span><br /><br /> <span data-ttu-id="2ae70-142">如果样式表包含脚本，脚本将保存到单独的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-142">If the style sheet contains scripts, the scripts are saved to a separate assembly.</span></span> <span data-ttu-id="2ae70-143">脚本程序集名称从主程序集名称生成。</span><span class="sxs-lookup"><span data-stu-id="2ae70-143">Script assembly names are generated from the main assembly name.</span></span> <span data-ttu-id="2ae70-144">例如，如果您为程序集名称指定了 CustOrders.dll，则第一个脚本程序集命名为 CustOrders_Script1.dll。</span><span class="sxs-lookup"><span data-stu-id="2ae70-144">For example, if you specified CustOrders.dll for your assembly name, the first script assembly is named CustOrders_Script1.dll.</span></span>|  
|<span data-ttu-id="2ae70-145">`/settings:` `document+-, script+-, DTD+-,`</span><span class="sxs-lookup"><span data-stu-id="2ae70-145">`/settings:` `document+-, script+-, DTD+-,`</span></span>|<span data-ttu-id="2ae70-146">指定是否允许在样式表中使用 `document()` 函数、XSLT 脚本或文档类型定义 (DTD)。</span><span class="sxs-lookup"><span data-stu-id="2ae70-146">Specifies whether to allow `document()` functions, XSLT script, or document type definition (DTD) in the style sheet.</span></span><br /><br /> <span data-ttu-id="2ae70-147">默认行为禁用对 DTD、`document()` 函数和脚本的支持。</span><span class="sxs-lookup"><span data-stu-id="2ae70-147">The default behavior disables support for DTD, the `document()` function and scripting.</span></span>|  
|<span data-ttu-id="2ae70-148">`@` `file`</span><span class="sxs-lookup"><span data-stu-id="2ae70-148">`@` `file`</span></span>|<span data-ttu-id="2ae70-149">允许您指定包含编译器选项的文件。</span><span class="sxs-lookup"><span data-stu-id="2ae70-149">Lets you specify a file that contains the compiler options.</span></span>|  
|`?`|<span data-ttu-id="2ae70-150">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="2ae70-150">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ae70-151">备注</span><span class="sxs-lookup"><span data-stu-id="2ae70-151">Remarks</span></span>  
 <span data-ttu-id="2ae70-152">XSLT 解决方案可由多个样式表模块组成。</span><span class="sxs-lookup"><span data-stu-id="2ae70-152">XSLT solutions can consist of multiple style sheet modules.</span></span> <span data-ttu-id="2ae70-153">xsltc.exe 工具从样式表生成程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-153">The xsltc.exe tool generates assemblies from style sheets.</span></span> <span data-ttu-id="2ae70-154">然后可以将程序集传递到 <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> 方法中。</span><span class="sxs-lookup"><span data-stu-id="2ae70-154">The assemblies can then be passed into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2ae70-155">这有助于在一些 XSLT 部署方案中降低性能成本。</span><span class="sxs-lookup"><span data-stu-id="2ae70-155">This can help decrease performance costs in some XSLT deployment scenarios.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ae70-156">您还必须包括已编译的程序集作为应用程序中的引用。</span><span class="sxs-lookup"><span data-stu-id="2ae70-156">You must also include the compiled assembly as a reference in your application.</span></span>  
  
 <span data-ttu-id="2ae70-157">Xsltc.exe 工具不会验证类 (`/class:``name`) 或程序集 (`/out:``assemblyName`) 名称。</span><span class="sxs-lookup"><span data-stu-id="2ae70-157">The xsltc.exe tool does not validate the class (`/class:``name`) or assembly (`/out:``assemblyName`) names.</span></span> <span data-ttu-id="2ae70-158">如果名称无效，公共语言运行库将引发错误。</span><span class="sxs-lookup"><span data-stu-id="2ae70-158">Errors are thrown by the common language runtime if the names are not valid.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2ae70-159">示例</span><span class="sxs-lookup"><span data-stu-id="2ae70-159">Examples</span></span>  
 <span data-ttu-id="2ae70-160">下面的命令编译样式表并创建一个名为 booksort.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-160">The following command compiles the style sheet and creates an assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl  
```  
  
 <span data-ttu-id="2ae70-161">下面的命令编译样式表并创建名称分别为 booksort.dll 和 booksort.pdb 的程序集和 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="2ae70-161">The following command compiles the style sheet and creates an assembly and PDB file that are named booksort.dll and booksort.pdb respectively.</span></span>  
  
```  
xsltc booksort.xsl /debug  
```  
  
 <span data-ttu-id="2ae70-162">下面的命令编译包含 msxsl:script 元素的样式表并创建两个名为 calc.dll 和 calc_Script1.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-162">The following command compiles a style sheet that contains an msxsl:script element and creates two assemblies named calc.dll and calc_Script1.dll.</span></span>  
  
```  
xsltc /settings:script+ calc.xsl  
```  
  
 <span data-ttu-id="2ae70-163">下面的命令启用 DTD 处理和脚本支持并创建两个名为 myTest.dll 和 myTest_Script1.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-163">The following command enables DTD processing and script support and creates two assemblies named myTest.dll and myTest_Script1.dll.</span></span>  
  
```  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 <span data-ttu-id="2ae70-164">下面的命令编译两个样式表模块并创建单个名为 booksort.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="2ae70-164">The following command compiles two style sheet modules and creates a single assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ae70-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae70-165">See Also</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [<span data-ttu-id="2ae70-166">如何： 通过使用程序集执行 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="2ae70-166">How to: Perform an XSLT Transformation by Using an Assembly</span></span>](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)  
 [<span data-ttu-id="2ae70-167">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="2ae70-167">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
