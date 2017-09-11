---
title: "/linkresource (Visual Basic 中) |Microsoft 文档"
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
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d4d2d2fdacef0c830414790efa544a96c35fd3c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="8714d-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8714d-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="8714d-103">创建指向托管资源的链接。</span><span class="sxs-lookup"><span data-stu-id="8714d-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8714d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8714d-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8714d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8714d-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="8714d-106">必需。</span><span class="sxs-lookup"><span data-stu-id="8714d-106">Required.</span></span> <span data-ttu-id="8714d-107">要链接到程序集的资源文件。</span><span class="sxs-lookup"><span data-stu-id="8714d-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="8714d-108">如果文件名包含空格，则将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="8714d-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="8714d-109">可选。</span><span class="sxs-lookup"><span data-stu-id="8714d-109">Optional.</span></span> <span data-ttu-id="8714d-110">资源的逻辑名称。</span><span class="sxs-lookup"><span data-stu-id="8714d-110">The logical name for the resource.</span></span> <span data-ttu-id="8714d-111">用于加载资源名称。</span><span class="sxs-lookup"><span data-stu-id="8714d-111">The name that is used to load the resource.</span></span> <span data-ttu-id="8714d-112">默认值是该文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8714d-112">The default is the name of the file.</span></span> <span data-ttu-id="8714d-113">或者，您可以指定文件是否是公共的还是私有的程序集清单，例如︰ `/linkres:filename.res,myname.res,public`。</span><span class="sxs-lookup"><span data-stu-id="8714d-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="8714d-114">默认情况下，`filename`在程序集是公共的。</span><span class="sxs-lookup"><span data-stu-id="8714d-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8714d-115">备注</span><span class="sxs-lookup"><span data-stu-id="8714d-115">Remarks</span></span>  
 <span data-ttu-id="8714d-116">`/linkresource`选项不会在输出文件中嵌入的资源文件; 使用`/resource`选项以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8714d-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="8714d-117">`/linkresource`选项需要一个`/target`以外选项`/target:module`。</span><span class="sxs-lookup"><span data-stu-id="8714d-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="8714d-118">如果`filename`是[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]创建资源文件，例如，通过[Resgen.exe （资源文件生成器）](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，它可以访问其成员保持<xref:System.Resources>命名空间。</xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="8714d-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="8714d-119">(有关详细信息，请参阅<xref:System.Resources.ResourceManager>。)</xref:System.Resources.ResourceManager>若要在运行时访问所有其他资源，使用的方法，以开始`GetManifestResource`中<xref:System.Reflection.Assembly>类。</xref:System.Reflection.Assembly></span><span class="sxs-lookup"><span data-stu-id="8714d-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="8714d-120">文件名称可以是任何文件格式。</span><span class="sxs-lookup"><span data-stu-id="8714d-120">The file name can be any file format.</span></span> <span data-ttu-id="8714d-121">例如，您可能想要使本机 DLL 程序集的一部分，以便它可以安装到全局程序集缓存中并从程序集中的托管代码访问。</span><span class="sxs-lookup"><span data-stu-id="8714d-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="8714d-122">缩写形式`/linkresource`是`/linkres`。</span><span class="sxs-lookup"><span data-stu-id="8714d-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8714d-123">`/linkresource`选项不可用从 Visual Studio 开发环境，可仅编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="8714d-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8714d-124">示例</span><span class="sxs-lookup"><span data-stu-id="8714d-124">Example</span></span>  
 <span data-ttu-id="8714d-125">下面的代码编译`In.vb`并链接到资源文件`Rf.resource`。</span><span class="sxs-lookup"><span data-stu-id="8714d-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8714d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8714d-126">See Also</span></span>  
 <span data-ttu-id="8714d-127">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8714d-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8714d-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="8714d-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="8714d-129"> [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span><span class="sxs-lookup"><span data-stu-id="8714d-129"> [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span></span>  
<span data-ttu-id="8714d-130"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="8714d-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
