---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924864"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="a3377-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3377-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="a3377-103">创建指向托管资源的链接。</span><span class="sxs-lookup"><span data-stu-id="a3377-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3377-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3377-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a3377-105">自变量</span><span class="sxs-lookup"><span data-stu-id="a3377-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a3377-106">必需。</span><span class="sxs-lookup"><span data-stu-id="a3377-106">Required.</span></span> <span data-ttu-id="a3377-107">要链接到程序集的资源文件。</span><span class="sxs-lookup"><span data-stu-id="a3377-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="a3377-108">如果文件名包含空格, 则将该名称括在引号 ("") 中。</span><span class="sxs-lookup"><span data-stu-id="a3377-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="a3377-109">可选。</span><span class="sxs-lookup"><span data-stu-id="a3377-109">Optional.</span></span> <span data-ttu-id="a3377-110">资源的逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="a3377-110">The logical name for the resource.</span></span> <span data-ttu-id="a3377-111">用于加载资源的名称。</span><span class="sxs-lookup"><span data-stu-id="a3377-111">The name that is used to load the resource.</span></span> <span data-ttu-id="a3377-112">默认值是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a3377-112">The default is the name of the file.</span></span> <span data-ttu-id="a3377-113">您也可以在程序集清单中指定文件是公共的还是私有的, 例如: `-linkres:filename.res,myname.res,public`。</span><span class="sxs-lookup"><span data-stu-id="a3377-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="a3377-114">默认情况下`filename` , 在程序集中是公共的。</span><span class="sxs-lookup"><span data-stu-id="a3377-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3377-115">备注</span><span class="sxs-lookup"><span data-stu-id="a3377-115">Remarks</span></span>  
 <span data-ttu-id="a3377-116">此选项不会将资源文件嵌入到输出文件中; `-resource`请使用选项执行此操作。 `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="a3377-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="a3377-117">选项需要的`-target` 选项`-target:module`之一除外。 `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="a3377-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="a3377-118">如果`filename`是通过[resgen.exe (资源文件生成器)](../../../framework/tools/resgen-exe-resource-file-generator.md)或在开发环境中创建的 .NET Framework 资源文件, 则可以<xref:System.Resources>使用命名空间中的成员来访问它。</span><span class="sxs-lookup"><span data-stu-id="a3377-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="a3377-119">（有关详细信息，请参阅 <xref:System.Resources.ResourceManager>。）若要在运行时访问所有其他资源, 请使用`GetManifestResource` <xref:System.Reflection.Assembly>类中以开头的方法。</span><span class="sxs-lookup"><span data-stu-id="a3377-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="a3377-120">文件名可以是任何文件格式。</span><span class="sxs-lookup"><span data-stu-id="a3377-120">The file name can be any file format.</span></span> <span data-ttu-id="a3377-121">例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。</span><span class="sxs-lookup"><span data-stu-id="a3377-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="a3377-122">`-linkresource` 的缩写形式是 `-linkres`。</span><span class="sxs-lookup"><span data-stu-id="a3377-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3377-123">此`-linkresource`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="a3377-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3377-124">示例</span><span class="sxs-lookup"><span data-stu-id="a3377-124">Example</span></span>  
 <span data-ttu-id="a3377-125">下面的代码将`in.vb`编译和链接到资源`rf.resource`文件。</span><span class="sxs-lookup"><span data-stu-id="a3377-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3377-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3377-126">See also</span></span>

- [<span data-ttu-id="a3377-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="a3377-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a3377-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3377-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="a3377-129">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3377-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="a3377-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="a3377-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
