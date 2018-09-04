---
title: -资源 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77c80332e663596244b35fe002218e7bcbaeb46a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523319"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="f5a0e-102">-资源 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a0e-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="f5a0e-103">将托管资源嵌入程序集。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5a0e-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5a0e-105">自变量</span><span class="sxs-lookup"><span data-stu-id="f5a0e-105">Arguments</span></span>  
  
|<span data-ttu-id="f5a0e-106">术语</span><span class="sxs-lookup"><span data-stu-id="f5a0e-106">Term</span></span>|<span data-ttu-id="f5a0e-107">定义</span><span class="sxs-lookup"><span data-stu-id="f5a0e-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="f5a0e-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-108">Required.</span></span> <span data-ttu-id="f5a0e-109">要在输出文件中嵌入的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="f5a0e-110">默认情况下，`filename`在程序集是公共的。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="f5a0e-111">将文件名括在引号 ("") 如果包含空格。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="f5a0e-112">可选。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-112">Optional.</span></span> <span data-ttu-id="f5a0e-113">资源; 的逻辑名称用来加载它的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="f5a0e-114">默认值是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-114">The default is the name of the file.</span></span> <span data-ttu-id="f5a0e-115">或者，可以指定资源是公共或私有程序集清单中与以下一样： `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="f5a0e-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a0e-116">备注</span><span class="sxs-lookup"><span data-stu-id="f5a0e-116">Remarks</span></span>  
 <span data-ttu-id="f5a0e-117">使用`-linkresource`若要将资源链接到程序集，而无需将资源文件放置在输出文件。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="f5a0e-118">如果`filename`是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]创建的资源文件，例如，通过[Resgen.exe （资源文件生成器）](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，则可以使用来访问中的成员<xref:System.Resources>命名空间 （请参阅<xref:System.Resources.ResourceManager>有关详细信息)。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="f5a0e-119">若要在运行时访问所有其他资源，请使用以下方法之一： <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>， <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>，或<xref:System.Reflection.Assembly.GetManifestResourceStream%2A>。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="f5a0e-120">`-resource` 的缩写形式是 `-res`。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="f5a0e-121">有关如何设置的信息`-resource`在 Visual Studio IDE 中，请参阅[管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a0e-122">示例</span><span class="sxs-lookup"><span data-stu-id="f5a0e-122">Example</span></span>  
 <span data-ttu-id="f5a0e-123">下面的代码编译`In.vb`和附加的资源文件`Rf.resource`。</span><span class="sxs-lookup"><span data-stu-id="f5a0e-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a0e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5a0e-124">See Also</span></span>  
 [<span data-ttu-id="f5a0e-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="f5a0e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f5a0e-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="f5a0e-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="f5a0e-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a0e-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="f5a0e-128">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a0e-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="f5a0e-129">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="f5a0e-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
