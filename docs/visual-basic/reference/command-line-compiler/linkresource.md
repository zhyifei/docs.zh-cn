---
title: /linkresource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="4fc64-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc64-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="4fc64-103">创建指向托管资源的链接。</span><span class="sxs-lookup"><span data-stu-id="4fc64-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc64-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fc64-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4fc64-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fc64-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="4fc64-106">必需。</span><span class="sxs-lookup"><span data-stu-id="4fc64-106">Required.</span></span> <span data-ttu-id="4fc64-107">要将链接到程序集的资源文件。</span><span class="sxs-lookup"><span data-stu-id="4fc64-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="4fc64-108">如果文件名包含空格，则将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="4fc64-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="4fc64-109">可选。</span><span class="sxs-lookup"><span data-stu-id="4fc64-109">Optional.</span></span> <span data-ttu-id="4fc64-110">资源的逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="4fc64-110">The logical name for the resource.</span></span> <span data-ttu-id="4fc64-111">用于加载资源的名称。</span><span class="sxs-lookup"><span data-stu-id="4fc64-111">The name that is used to load the resource.</span></span> <span data-ttu-id="4fc64-112">默认值是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4fc64-112">The default is the name of the file.</span></span> <span data-ttu-id="4fc64-113">或者，可以指定文件是否是公用或专用在程序集清单中，例如： `/linkres:filename.res,myname.res,public`。</span><span class="sxs-lookup"><span data-stu-id="4fc64-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="4fc64-114">默认情况下，`filename`在程序集是公共的。</span><span class="sxs-lookup"><span data-stu-id="4fc64-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc64-115">备注</span><span class="sxs-lookup"><span data-stu-id="4fc64-115">Remarks</span></span>  
 <span data-ttu-id="4fc64-116">`/linkresource`选项不会将资源文件嵌入到输出文件中; 使用`/resource`选项以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4fc64-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="4fc64-117">`/linkresource`选项需要一个`/target`选项以外`/target:module`。</span><span class="sxs-lookup"><span data-stu-id="4fc64-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="4fc64-118">如果`filename`是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]创建资源文件，例如，通过[Resgen.exe （资源文件生成器）](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，它可以访问其成员保持<xref:System.Resources>命名空间。</span><span class="sxs-lookup"><span data-stu-id="4fc64-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="4fc64-119">（有关详细信息，请参阅 <xref:System.Resources.ResourceManager>。）若要在运行时访问所有其他资源，使用的方法的开头`GetManifestResource`中<xref:System.Reflection.Assembly>类。</span><span class="sxs-lookup"><span data-stu-id="4fc64-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="4fc64-120">文件名称可以是任何文件格式。</span><span class="sxs-lookup"><span data-stu-id="4fc64-120">The file name can be any file format.</span></span> <span data-ttu-id="4fc64-121">例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。</span><span class="sxs-lookup"><span data-stu-id="4fc64-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="4fc64-122">`/linkresource` 的缩写形式是 `/linkres`。</span><span class="sxs-lookup"><span data-stu-id="4fc64-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fc64-123">`/linkresource`选项将不可用从 Visual Studio 开发环境，它可仅编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="4fc64-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fc64-124">示例</span><span class="sxs-lookup"><span data-stu-id="4fc64-124">Example</span></span>  
 <span data-ttu-id="4fc64-125">下面的代码编译`In.vb`并链接到资源文件`Rf.resource`。</span><span class="sxs-lookup"><span data-stu-id="4fc64-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fc64-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc64-126">See Also</span></span>  
 [<span data-ttu-id="4fc64-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4fc64-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4fc64-128">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc64-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="4fc64-129">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc64-129">/resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="4fc64-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4fc64-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
