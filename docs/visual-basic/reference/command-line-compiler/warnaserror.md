---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351711"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="23a2a-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a2a-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="23a2a-103">使编译器将第一次出现的警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="23a2a-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="23a2a-105">自变量</span><span class="sxs-lookup"><span data-stu-id="23a2a-105">Arguments</span></span>  
  
|<span data-ttu-id="23a2a-106">术语</span><span class="sxs-lookup"><span data-stu-id="23a2a-106">Term</span></span>|<span data-ttu-id="23a2a-107">定义</span><span class="sxs-lookup"><span data-stu-id="23a2a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="23a2a-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="23a2a-108">+ &#124; -</span></span>|<span data-ttu-id="23a2a-109">可选。</span><span class="sxs-lookup"><span data-stu-id="23a2a-109">Optional.</span></span> <span data-ttu-id="23a2a-110">默认情况下，`-warnaserror-` 生效；警告不会阻止编译器生成输出文件。</span><span class="sxs-lookup"><span data-stu-id="23a2a-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="23a2a-111">`-warnaserror` 选项与 `-warnaserror+` 相同，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="23a2a-112">可选。</span><span class="sxs-lookup"><span data-stu-id="23a2a-112">Optional.</span></span> <span data-ttu-id="23a2a-113">`-warnaserror` 选项适用的警告 ID 编号列表，以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="23a2a-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="23a2a-114">如果未指定警告 ID，则 `-warnaserror` 选项适用于所有警告。</span><span class="sxs-lookup"><span data-stu-id="23a2a-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23a2a-115">备注</span><span class="sxs-lookup"><span data-stu-id="23a2a-115">Remarks</span></span>  
 <span data-ttu-id="23a2a-116">`-warnaserror` 选项将所有警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="23a2a-117">通常将报告为警告的任何消息都报告为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="23a2a-118">编译器将随后出现的相同警告报告为警告。</span><span class="sxs-lookup"><span data-stu-id="23a2a-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="23a2a-119">默认情况下，`-warnaserror-` 生效，导致警告仅提供信息。</span><span class="sxs-lookup"><span data-stu-id="23a2a-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="23a2a-120">`-warnaserror` 选项与 `-warnaserror+` 相同，会导致将警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="23a2a-121">如果希望仅将一些特定警告视为错误，则可以指定视为错误的警告编号的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="23a2a-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23a2a-122">`-warnaserror` 选项不控制警告的显示方式。</span><span class="sxs-lookup"><span data-stu-id="23a2a-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="23a2a-123">使用 [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 选项来禁用警告。</span><span class="sxs-lookup"><span data-stu-id="23a2a-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="23a2a-124">设置 -warnaserror 以将所有警告视为 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="23a2a-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="23a2a-125">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="23a2a-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="23a2a-126">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="23a2a-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="23a2a-127">2.  Click the **Compile** tab.</span><span class="sxs-lookup"><span data-stu-id="23a2a-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="23a2a-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span><span class="sxs-lookup"><span data-stu-id="23a2a-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="23a2a-129">4.  Check the **Treat all warnings as errors** check box.</span><span class="sxs-lookup"><span data-stu-id="23a2a-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="23a2a-130">设置 -warnaserror 以将特定警告视为 Visual Studio IDE 中的错误</span><span class="sxs-lookup"><span data-stu-id="23a2a-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="23a2a-131">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="23a2a-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="23a2a-132">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="23a2a-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="23a2a-133">2.  Click the **Compile** tab.</span><span class="sxs-lookup"><span data-stu-id="23a2a-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="23a2a-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span><span class="sxs-lookup"><span data-stu-id="23a2a-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="23a2a-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span><span class="sxs-lookup"><span data-stu-id="23a2a-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="23a2a-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span><span class="sxs-lookup"><span data-stu-id="23a2a-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23a2a-137">示例</span><span class="sxs-lookup"><span data-stu-id="23a2a-137">Example</span></span>  
 <span data-ttu-id="23a2a-138">以下代码编译 `In.vb` 并指示编译器在第一次发现每个警告时显示错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="23a2a-139">示例</span><span class="sxs-lookup"><span data-stu-id="23a2a-139">Example</span></span>  
 <span data-ttu-id="23a2a-140">以下代码编译 `T2.vb` 并仅将未使用的本地变量 (42024) 的警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="23a2a-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="23a2a-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="23a2a-141">See also</span></span>

- [<span data-ttu-id="23a2a-142">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="23a2a-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="23a2a-143">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="23a2a-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="23a2a-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23a2a-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
