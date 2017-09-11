---
title: "/rootnamespace |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
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
ms.openlocfilehash: 9a7a26407e981d3aea58d970d88bf25025e6bba6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="rootnamespace"></a><span data-ttu-id="95113-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="95113-102">/rootnamespace</span></span>
<span data-ttu-id="95113-103">指定所有类型声明的命名空间。</span><span class="sxs-lookup"><span data-stu-id="95113-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95113-104">语法</span><span class="sxs-lookup"><span data-stu-id="95113-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="95113-105">参数</span><span class="sxs-lookup"><span data-stu-id="95113-105">Arguments</span></span>  
  
|<span data-ttu-id="95113-106">术语</span><span class="sxs-lookup"><span data-stu-id="95113-106">Term</span></span>|<span data-ttu-id="95113-107">定义</span><span class="sxs-lookup"><span data-stu-id="95113-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="95113-108">包含为当前项目的所有类型声明的命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="95113-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95113-109">备注</span><span class="sxs-lookup"><span data-stu-id="95113-109">Remarks</span></span>  
 <span data-ttu-id="95113-110">如果您使用 Visual Studio 可执行文件 (Devenv.exe) 来编译创建的项目在 Visual Studio 集成的开发环境中，使用`/rootnamespace`指定的值<xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>属性。</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="95113-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="95113-111">请参阅[Devenv 命令行开关](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="95113-111">See [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="95113-112">使用公共语言运行时 MSIL 反汇编程序 (我`ldasm.exe`) 以查看输出文件中的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="95113-112">Use the common language runtime MSIL Disassembler (I`ldasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="95113-113">在 Visual Studio 中设置 /rootnamespace 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="95113-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="95113-114">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="95113-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="95113-115">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="95113-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="95113-116">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="95113-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="95113-117">2.单击“应用程序” **** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="95113-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="95113-118">3.在修改此值**根 Namespace**框。</span><span class="sxs-lookup"><span data-stu-id="95113-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95113-119">示例</span><span class="sxs-lookup"><span data-stu-id="95113-119">Example</span></span>  
 <span data-ttu-id="95113-120">下面的代码编译`In.vb`和命名空间中包含所有类型声明`mynamespace`。</span><span class="sxs-lookup"><span data-stu-id="95113-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="95113-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95113-121">See Also</span></span>  
 <span data-ttu-id="95113-122">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="95113-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="95113-123"> [Ildasm.exe （IL 反汇编程序）](https://msdn.microsoft.com/library/f7dy01k1) </span><span class="sxs-lookup"><span data-stu-id="95113-123"> [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span></span>  
<span data-ttu-id="95113-124"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="95113-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
