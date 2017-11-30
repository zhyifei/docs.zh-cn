---
title: /warnaserror (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04b79b3d14a9c4a9f9721860cd1ed44032dfa5d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="ac291-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac291-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="ac291-103">使编译器将视为错误的警告的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="ac291-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac291-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac291-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac291-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac291-105">Arguments</span></span>  
  
|<span data-ttu-id="ac291-106">术语</span><span class="sxs-lookup"><span data-stu-id="ac291-106">Term</span></span>|<span data-ttu-id="ac291-107">定义</span><span class="sxs-lookup"><span data-stu-id="ac291-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ac291-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="ac291-108">+ &#124; -</span></span>|<span data-ttu-id="ac291-109">可选。</span><span class="sxs-lookup"><span data-stu-id="ac291-109">Optional.</span></span> <span data-ttu-id="ac291-110">默认情况下，`/warnaserror-`是有效，则警告不会阻止编译器生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="ac291-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="ac291-111">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="ac291-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="ac291-112">可选。</span><span class="sxs-lookup"><span data-stu-id="ac291-112">Optional.</span></span> <span data-ttu-id="ac291-113">以逗号分隔列表的警告 ID 号到`/warnaserror`选项适用。</span><span class="sxs-lookup"><span data-stu-id="ac291-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="ac291-114">如果不指定任何警告 ID，则`/warnaserror`选项适用于所有警告。</span><span class="sxs-lookup"><span data-stu-id="ac291-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac291-115">备注</span><span class="sxs-lookup"><span data-stu-id="ac291-115">Remarks</span></span>  
 <span data-ttu-id="ac291-116">`/warnaserror`选项将所有警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="ac291-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="ac291-117">任何将通常报告为警告而是会报告为错误的消息。</span><span class="sxs-lookup"><span data-stu-id="ac291-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="ac291-118">编译器将报告为警告相同的警告的后续匹配项。</span><span class="sxs-lookup"><span data-stu-id="ac291-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="ac291-119">默认情况下，`/warnaserror-`是起作用，这会导致仅为信息性的警告。</span><span class="sxs-lookup"><span data-stu-id="ac291-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="ac291-120">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="ac291-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="ac291-121">如果你想仅几个特定警告视为错误，则可以指定逗号分隔警告编号，以将视为错误的列表。</span><span class="sxs-lookup"><span data-stu-id="ac291-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac291-122">`/warnaserror`选项不控制如何显示警告。</span><span class="sxs-lookup"><span data-stu-id="ac291-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="ac291-123">使用[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)选项来禁用的警告。</span><span class="sxs-lookup"><span data-stu-id="ac291-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="ac291-124">若要设置 /warnaserror 将所有警告视为 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="ac291-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ac291-125">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="ac291-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ac291-126">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="ac291-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ac291-127">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="ac291-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="ac291-128">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="ac291-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ac291-129">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="ac291-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ac291-130">4.检查**将所有警告视为错误**复选框。</span><span class="sxs-lookup"><span data-stu-id="ac291-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="ac291-131">若要设置 /warnaserror 特定警告视为在 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="ac291-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ac291-132">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="ac291-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ac291-133">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="ac291-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="ac291-134">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="ac291-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ac291-135">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="ac291-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="ac291-136">4.请确保**将所有警告视为错误**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="ac291-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="ac291-137">5.选择**错误**从**通知**应被视为错误的警告旁边的列。</span><span class="sxs-lookup"><span data-stu-id="ac291-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac291-138">示例</span><span class="sxs-lookup"><span data-stu-id="ac291-138">Example</span></span>  
 <span data-ttu-id="ac291-139">下面的代码编译`In.vb`并指示编译器显示找到的每个警告的第一个匹配项错误。</span><span class="sxs-lookup"><span data-stu-id="ac291-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="ac291-140">示例</span><span class="sxs-lookup"><span data-stu-id="ac291-140">Example</span></span>  
 <span data-ttu-id="ac291-141">下面的代码编译`T2.vb`，并将仅对未使用的局部变量 (42024) 警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="ac291-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac291-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac291-142">See Also</span></span>  
 [<span data-ttu-id="ac291-143">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ac291-143">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ac291-144">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ac291-144">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="ac291-145">在 Visual Basic 中配置警告</span><span class="sxs-lookup"><span data-stu-id="ac291-145">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
