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
ms.openlocfilehash: 4f4b3db768b5466f8912b66a0a4709d0f773c1f3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554820"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="89f92-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f92-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="89f92-103">创建指向托管资源的链接。</span><span class="sxs-lookup"><span data-stu-id="89f92-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f92-104">语法</span><span class="sxs-lookup"><span data-stu-id="89f92-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="89f92-105">自变量</span><span class="sxs-lookup"><span data-stu-id="89f92-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="89f92-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="89f92-106">Required.</span></span> <span data-ttu-id="89f92-107">要链接到程序集的资源文件。</span><span class="sxs-lookup"><span data-stu-id="89f92-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="89f92-108">如果文件名包含空格，将名称括在引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="89f92-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="89f92-109">可选。</span><span class="sxs-lookup"><span data-stu-id="89f92-109">Optional.</span></span> <span data-ttu-id="89f92-110">资源的逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="89f92-110">The logical name for the resource.</span></span> <span data-ttu-id="89f92-111">用于加载资源名称。</span><span class="sxs-lookup"><span data-stu-id="89f92-111">The name that is used to load the resource.</span></span> <span data-ttu-id="89f92-112">默认值是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="89f92-112">The default is the name of the file.</span></span> <span data-ttu-id="89f92-113">或者，可以指定文件是否是公共或私有程序集清单，例如： `-linkres:filename.res,myname.res,public`。</span><span class="sxs-lookup"><span data-stu-id="89f92-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="89f92-114">默认情况下，`filename`在程序集是公共的。</span><span class="sxs-lookup"><span data-stu-id="89f92-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89f92-115">备注</span><span class="sxs-lookup"><span data-stu-id="89f92-115">Remarks</span></span>  
 <span data-ttu-id="89f92-116">`-linkresource`选项不会将资源文件嵌入到输出文件中; 使用`-resource`选项来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="89f92-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="89f92-117">`-linkresource`选项要求之一`-target`不是选项`-target:module`。</span><span class="sxs-lookup"><span data-stu-id="89f92-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="89f92-118">如果`filename`是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]创建的资源文件，例如，通过[Resgen.exe （资源文件生成器）](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，则可以使用来访问中的成员<xref:System.Resources>命名空间。</span><span class="sxs-lookup"><span data-stu-id="89f92-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="89f92-119">（有关详细信息，请参阅 <xref:System.Resources.ResourceManager>。）若要在运行时访问所有其他资源，使用的方法的开头`GetManifestResource`在<xref:System.Reflection.Assembly>类。</span><span class="sxs-lookup"><span data-stu-id="89f92-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="89f92-120">文件名称可以是任何文件格式。</span><span class="sxs-lookup"><span data-stu-id="89f92-120">The file name can be any file format.</span></span> <span data-ttu-id="89f92-121">例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。</span><span class="sxs-lookup"><span data-stu-id="89f92-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="89f92-122">`-linkresource` 的缩写形式是 `-linkres`。</span><span class="sxs-lookup"><span data-stu-id="89f92-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89f92-123">`-linkresource`选项不适用于从 Visual Studio 开发环境，便可仅在编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="89f92-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89f92-124">示例</span><span class="sxs-lookup"><span data-stu-id="89f92-124">Example</span></span>  
 <span data-ttu-id="89f92-125">下面的代码编译`in.vb`并链接到资源文件`rf.resource`。</span><span class="sxs-lookup"><span data-stu-id="89f92-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="89f92-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="89f92-126">See Also</span></span>  
 [<span data-ttu-id="89f92-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="89f92-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="89f92-128">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f92-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="89f92-129">-资源 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f92-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="89f92-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="89f92-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
