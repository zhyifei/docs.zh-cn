---
title: "/resource (Visual Basic 中) |Microsoft 文档"
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
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2278902f96f7b6349e91a9803f58c3caa89f4f33
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="resource-visual-basic"></a><span data-ttu-id="7944a-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7944a-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="7944a-103">将托管资源嵌入程序集。</span><span class="sxs-lookup"><span data-stu-id="7944a-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7944a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7944a-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7944a-105">参数</span><span class="sxs-lookup"><span data-stu-id="7944a-105">Arguments</span></span>  
  
|<span data-ttu-id="7944a-106">术语</span><span class="sxs-lookup"><span data-stu-id="7944a-106">Term</span></span>|<span data-ttu-id="7944a-107">定义</span><span class="sxs-lookup"><span data-stu-id="7944a-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="7944a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="7944a-108">Required.</span></span> <span data-ttu-id="7944a-109">要在输出文件中嵌入的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7944a-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="7944a-110">默认情况下，`filename`在程序集是公共的。</span><span class="sxs-lookup"><span data-stu-id="7944a-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="7944a-111">将文件名括在双引号 ("") 如果包含空格。</span><span class="sxs-lookup"><span data-stu-id="7944a-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="7944a-112">可选。</span><span class="sxs-lookup"><span data-stu-id="7944a-112">Optional.</span></span> <span data-ttu-id="7944a-113">资源; 的逻辑名称用来加载它的名称。</span><span class="sxs-lookup"><span data-stu-id="7944a-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="7944a-114">默认值是该文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7944a-114">The default is the name of the file.</span></span> <span data-ttu-id="7944a-115">或者，您可以指定资源与以下是否是公有或私有程序集清单中︰ `/res:``filename.res`，`myname.res`，`public`</span><span class="sxs-lookup"><span data-stu-id="7944a-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7944a-116">备注</span><span class="sxs-lookup"><span data-stu-id="7944a-116">Remarks</span></span>  
 <span data-ttu-id="7944a-117">使用`/linkresource`若要将资源链接到程序集，而无需将资源文件放置在输出文件。</span><span class="sxs-lookup"><span data-stu-id="7944a-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="7944a-118">如果`filename`是[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]创建资源文件，例如，通过[Resgen.exe （资源文件生成器）](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，它可以访问其成员保持<xref:System.Resources>命名空间 (请参阅<xref:System.Resources.ResourceManager>有关详细信息)。</xref:System.Resources.ResourceManager> </xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="7944a-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="7944a-119">若要在运行时访问所有其他资源，请使用以下方法之一︰ <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>， <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>，或<xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A></span><span class="sxs-lookup"><span data-stu-id="7944a-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="7944a-120">缩写形式`/resource`是`/res`。</span><span class="sxs-lookup"><span data-stu-id="7944a-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="7944a-121">有关如何设置`/resource`在 Visual Studio IDE 中，请参阅[管理应用程序资源 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="7944a-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7944a-122">示例</span><span class="sxs-lookup"><span data-stu-id="7944a-122">Example</span></span>  
 <span data-ttu-id="7944a-123">下面的代码编译`In.vb`和附加的资源文件`Rf.resource`。</span><span class="sxs-lookup"><span data-stu-id="7944a-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7944a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7944a-124">See Also</span></span>  
 <span data-ttu-id="7944a-125">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="7944a-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="7944a-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span><span class="sxs-lookup"><span data-stu-id="7944a-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span></span>  
<span data-ttu-id="7944a-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span><span class="sxs-lookup"><span data-stu-id="7944a-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span></span>  
<span data-ttu-id="7944a-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="7944a-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="7944a-129"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="7944a-129"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
