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
ms.openlocfilehash: d472795affe0df098d1551daf51a2f0ae20723ba
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="5a010-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a010-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="5a010-103">使编译器将视为错误的警告的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="5a010-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a010-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a010-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a010-105">自变量</span><span class="sxs-lookup"><span data-stu-id="5a010-105">Arguments</span></span>  
  
|<span data-ttu-id="5a010-106">术语</span><span class="sxs-lookup"><span data-stu-id="5a010-106">Term</span></span>|<span data-ttu-id="5a010-107">定义</span><span class="sxs-lookup"><span data-stu-id="5a010-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="5a010-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="5a010-108">+ &#124; -</span></span>|<span data-ttu-id="5a010-109">可选。</span><span class="sxs-lookup"><span data-stu-id="5a010-109">Optional.</span></span> <span data-ttu-id="5a010-110">默认情况下，`/warnaserror-`是有效，则警告不会阻止编译器生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="5a010-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="5a010-111">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="5a010-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="5a010-112">可选。</span><span class="sxs-lookup"><span data-stu-id="5a010-112">Optional.</span></span> <span data-ttu-id="5a010-113">以逗号分隔列表的警告 ID 号到`/warnaserror`选项适用。</span><span class="sxs-lookup"><span data-stu-id="5a010-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="5a010-114">如果不指定任何警告 ID，则`/warnaserror`选项适用于所有警告。</span><span class="sxs-lookup"><span data-stu-id="5a010-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a010-115">备注</span><span class="sxs-lookup"><span data-stu-id="5a010-115">Remarks</span></span>  
 <span data-ttu-id="5a010-116">`/warnaserror`选项将所有警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="5a010-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="5a010-117">任何将通常报告为警告而是会报告为错误的消息。</span><span class="sxs-lookup"><span data-stu-id="5a010-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="5a010-118">编译器将报告为警告相同的警告的后续匹配项。</span><span class="sxs-lookup"><span data-stu-id="5a010-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="5a010-119">默认情况下，`/warnaserror-`是起作用，这会导致仅为信息性的警告。</span><span class="sxs-lookup"><span data-stu-id="5a010-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="5a010-120">`/warnaserror`选项，这是相同作为`/warnaserror+`，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="5a010-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="5a010-121">如果你想仅几个特定警告视为错误，则可以指定逗号分隔警告编号，以将视为错误的列表。</span><span class="sxs-lookup"><span data-stu-id="5a010-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a010-122">`/warnaserror`选项不控制如何显示警告。</span><span class="sxs-lookup"><span data-stu-id="5a010-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="5a010-123">使用[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)选项来禁用的警告。</span><span class="sxs-lookup"><span data-stu-id="5a010-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="5a010-124">若要设置 /warnaserror 将所有警告视为 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="5a010-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="5a010-125">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="5a010-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5a010-126">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="5a010-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5a010-127">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a010-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5a010-128">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="5a010-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="5a010-129">4.检查**将所有警告视为错误**复选框。</span><span class="sxs-lookup"><span data-stu-id="5a010-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="5a010-130">若要设置 /warnaserror 特定警告视为在 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="5a010-130">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="5a010-131">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="5a010-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5a010-132">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="5a010-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="5a010-133">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a010-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5a010-134">3.请确保**禁用所有警告**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="5a010-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="5a010-135">4.请确保**将所有警告视为错误**复选框处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="5a010-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="5a010-136">5.选择**错误**从**通知**应被视为错误的警告旁边的列。</span><span class="sxs-lookup"><span data-stu-id="5a010-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a010-137">示例</span><span class="sxs-lookup"><span data-stu-id="5a010-137">Example</span></span>  
 <span data-ttu-id="5a010-138">下面的代码编译`In.vb`并指示编译器显示找到的每个警告的第一个匹配项错误。</span><span class="sxs-lookup"><span data-stu-id="5a010-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="5a010-139">示例</span><span class="sxs-lookup"><span data-stu-id="5a010-139">Example</span></span>  
 <span data-ttu-id="5a010-140">下面的代码编译`T2.vb`，并将仅对未使用的局部变量 (42024) 警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="5a010-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a010-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a010-141">See Also</span></span>  
 [<span data-ttu-id="5a010-142">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5a010-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="5a010-143">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="5a010-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="5a010-144">在 Visual Basic 中配置警告</span><span class="sxs-lookup"><span data-stu-id="5a010-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
