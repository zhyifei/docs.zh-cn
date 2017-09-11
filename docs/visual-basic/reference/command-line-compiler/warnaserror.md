---
title: "/warnaserror (Visual Basic 中) |Microsoft 文档"
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
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
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
ms.openlocfilehash: 8ed72415a75860b34e37c2bf4fc686cdae37f69e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="95ffd-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95ffd-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="95ffd-103">使编译器将视为错误的警告的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="95ffd-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="95ffd-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="95ffd-105">参数</span><span class="sxs-lookup"><span data-stu-id="95ffd-105">Arguments</span></span>  
  
|<span data-ttu-id="95ffd-106">术语</span><span class="sxs-lookup"><span data-stu-id="95ffd-106">Term</span></span>|<span data-ttu-id="95ffd-107">定义</span><span class="sxs-lookup"><span data-stu-id="95ffd-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="95ffd-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="95ffd-108">+ &#124; -</span></span>|<span data-ttu-id="95ffd-109">可选。</span><span class="sxs-lookup"><span data-stu-id="95ffd-109">Optional.</span></span> <span data-ttu-id="95ffd-110">默认情况下，`/warnaserror-`是有效，则警告不会阻止编译器生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="95ffd-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="95ffd-111">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="95ffd-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="95ffd-112">可选。</span><span class="sxs-lookup"><span data-stu-id="95ffd-112">Optional.</span></span> <span data-ttu-id="95ffd-113">以逗号分隔的多个警告 ID 号向其`/warnaserror`选项适用。</span><span class="sxs-lookup"><span data-stu-id="95ffd-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="95ffd-114">如果指定无警告 ID，则`/warnaserror`选项适用于所有警告。</span><span class="sxs-lookup"><span data-stu-id="95ffd-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95ffd-115">备注</span><span class="sxs-lookup"><span data-stu-id="95ffd-115">Remarks</span></span>  
 <span data-ttu-id="95ffd-116">`/warnaserror`选项将所有警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="95ffd-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="95ffd-117">将通常报告为警告都视为错误报告的任何消息。</span><span class="sxs-lookup"><span data-stu-id="95ffd-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="95ffd-118">编译器将报告为警告相同的警告的后续匹配项。</span><span class="sxs-lookup"><span data-stu-id="95ffd-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="95ffd-119">默认情况下，`/warnaserror-`是起作用，则会导致只是信息性警告。</span><span class="sxs-lookup"><span data-stu-id="95ffd-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="95ffd-120">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="95ffd-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="95ffd-121">如果您希望仅将一些特定警告视为错误，您可以指定逗号分隔警告编号，以将视为错误的列表。</span><span class="sxs-lookup"><span data-stu-id="95ffd-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95ffd-122">`/warnaserror`选项不控制如何显示警告。</span><span class="sxs-lookup"><span data-stu-id="95ffd-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="95ffd-123">使用[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)选项可禁用警告。</span><span class="sxs-lookup"><span data-stu-id="95ffd-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="95ffd-124">若要设置 /warnaserror 将所有警告视为 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="95ffd-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="95ffd-125">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="95ffd-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="95ffd-126">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="95ffd-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="95ffd-127">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="95ffd-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="95ffd-128">2.单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="95ffd-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="95ffd-129">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="95ffd-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="95ffd-130">4.检查**将所有警告视为错误**复选框。</span><span class="sxs-lookup"><span data-stu-id="95ffd-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="95ffd-131">若要设置 /warnaserror 特定警告视为错误在 Visual Studio IDE 中</span><span class="sxs-lookup"><span data-stu-id="95ffd-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="95ffd-132">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="95ffd-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="95ffd-133">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="95ffd-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="95ffd-134">2.单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="95ffd-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="95ffd-135">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="95ffd-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="95ffd-136">4.请确保**将所有警告视为错误**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="95ffd-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="95ffd-137">5.选择**错误**从**通知**列应被视为错误的警告旁边。</span><span class="sxs-lookup"><span data-stu-id="95ffd-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95ffd-138">示例</span><span class="sxs-lookup"><span data-stu-id="95ffd-138">Example</span></span>  
 <span data-ttu-id="95ffd-139">下面的代码编译`In.vb`并指示编译器显示为它找到的每个警告的首次出现的错误。</span><span class="sxs-lookup"><span data-stu-id="95ffd-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="95ffd-140">示例</span><span class="sxs-lookup"><span data-stu-id="95ffd-140">Example</span></span>  
 <span data-ttu-id="95ffd-141">下面的代码编译`T2.vb`和仅对未使用的局部变量 (42024) 警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="95ffd-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="95ffd-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95ffd-142">See Also</span></span>  
 <span data-ttu-id="95ffd-143">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="95ffd-143">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="95ffd-144"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="95ffd-144"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="95ffd-145"> [在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="95ffd-145"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
