---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="525c3-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="525c3-102">/rootnamespace</span></span>
<span data-ttu-id="525c3-103">指定所有类型声明的命名空间。</span><span class="sxs-lookup"><span data-stu-id="525c3-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="525c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="525c3-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="525c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="525c3-105">Arguments</span></span>  
  
|<span data-ttu-id="525c3-106">术语</span><span class="sxs-lookup"><span data-stu-id="525c3-106">Term</span></span>|<span data-ttu-id="525c3-107">定义</span><span class="sxs-lookup"><span data-stu-id="525c3-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="525c3-108">在包含为当前项目的所有类型声明的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="525c3-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="525c3-109">备注</span><span class="sxs-lookup"><span data-stu-id="525c3-109">Remarks</span></span>  
 <span data-ttu-id="525c3-110">如果你使用 Visual Studio 可执行文件 (Devenv.exe) 来编译创建的项目在 Visual Studio 集成的开发环境中，使用`/rootnamespace`以指定的值<xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="525c3-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="525c3-111">请参阅[Devenv 命令行开关](/visualstudio/ide/reference/devenv-command-line-switches)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="525c3-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="525c3-112">使用公共语言运行时 MSIL 反汇编程序 (`Ildasm.exe`) 若要查看你的输出文件中的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="525c3-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="525c3-113">在 Visual Studio 中设置 /rootnamespace 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="525c3-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="525c3-114">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="525c3-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="525c3-115">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="525c3-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="525c3-116">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="525c3-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="525c3-117">2.单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="525c3-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="525c3-118">3.修改中的值**根 Namespace**框。</span><span class="sxs-lookup"><span data-stu-id="525c3-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="525c3-119">示例</span><span class="sxs-lookup"><span data-stu-id="525c3-119">Example</span></span>  
 <span data-ttu-id="525c3-120">下面的代码编译`In.vb`和命名空间中包含所有类型声明`mynamespace`。</span><span class="sxs-lookup"><span data-stu-id="525c3-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="525c3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="525c3-121">See Also</span></span>  
 [<span data-ttu-id="525c3-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="525c3-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="525c3-123">Ildasm.exe（IL 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="525c3-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="525c3-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="525c3-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
