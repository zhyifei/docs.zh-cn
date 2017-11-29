---
title: /langversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a><span data-ttu-id="6b33d-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b33d-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="6b33d-103">使编译器接受指定的 Visual Basic 语言版本中包含的语法。</span><span class="sxs-lookup"><span data-stu-id="6b33d-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b33d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b33d-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b33d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b33d-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="6b33d-106">必需。</span><span class="sxs-lookup"><span data-stu-id="6b33d-106">Required.</span></span> <span data-ttu-id="6b33d-107">要在编译期间使用的语言版本。</span><span class="sxs-lookup"><span data-stu-id="6b33d-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="6b33d-108">接受的值是`9`， `9.0`， `10`，和`10.0`。</span><span class="sxs-lookup"><span data-stu-id="6b33d-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b33d-109">备注</span><span class="sxs-lookup"><span data-stu-id="6b33d-109">Remarks</span></span>  
 <span data-ttu-id="6b33d-110">`/langversion`选项指定编译器接受哪些语法。</span><span class="sxs-lookup"><span data-stu-id="6b33d-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="6b33d-111">例如，如果你指定的语言版本为 9.0，编译器将生成有关仅在版本 10.0 中有效和更高版本的语法错误。</span><span class="sxs-lookup"><span data-stu-id="6b33d-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="6b33d-112">当你面向不同版本的.NET framework 开发应用程序时，你可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="6b33d-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="6b33d-113">例如，如果你正面向.NET Framework 3.5，你可以使用此选项以确保不使用从语言版本 10.0 的语法。</span><span class="sxs-lookup"><span data-stu-id="6b33d-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="6b33d-114">你可以设置`/langversion`直接只能通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="6b33d-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="6b33d-115">有关详细信息，请参阅[面向特定的 .NET Framework 版本](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)。</span><span class="sxs-lookup"><span data-stu-id="6b33d-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b33d-116">示例</span><span class="sxs-lookup"><span data-stu-id="6b33d-116">Example</span></span>  
 <span data-ttu-id="6b33d-117">下面的代码编译`sample.vb`对于 Visual Basic 9.0 版。</span><span class="sxs-lookup"><span data-stu-id="6b33d-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b33d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b33d-118">See Also</span></span>  
 [<span data-ttu-id="6b33d-119">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="6b33d-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6b33d-120">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="6b33d-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6b33d-121">面向特定的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="6b33d-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
