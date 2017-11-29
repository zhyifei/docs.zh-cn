---
title: "正则表达式活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edeb55f25abf9e6f22ebfe1d0ea63eb07ba0f203
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-activities"></a><span data-ttu-id="51933-102">正则表达式活动</span><span class="sxs-lookup"><span data-stu-id="51933-102">Regular Expression Activities</span></span>
<span data-ttu-id="51933-103">此示例演示如何一组活动，这些活动公开 <xref:System.Text.RegularExpressions> 命名空间的正则表达式功能。</span><span class="sxs-lookup"><span data-stu-id="51933-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="51933-104">这些自定义活动可以在工作流应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="51933-104">These custom activities can be used within a workflow application.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="51933-105">正则表达式，请参阅[N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace。</span><span class="sxs-lookup"><span data-stu-id="51933-105"> regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="51933-106">下表详细介绍了此示例中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="51933-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="51933-107">Activity</span><span class="sxs-lookup"><span data-stu-id="51933-107">Activity</span></span>|<span data-ttu-id="51933-108">描述</span><span class="sxs-lookup"><span data-stu-id="51933-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="51933-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="51933-109">IsMatch</span></span>|<span data-ttu-id="51933-110">指定正则表达式是否在输入字符串中找到了匹配项。</span><span class="sxs-lookup"><span data-stu-id="51933-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="51933-111">匹配</span><span class="sxs-lookup"><span data-stu-id="51933-111">Matches</span></span>|<span data-ttu-id="51933-112">在输入字符串中搜索所有正则表达式，然后返回所有成功的匹配项。</span><span class="sxs-lookup"><span data-stu-id="51933-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="51933-113">替换</span><span class="sxs-lookup"><span data-stu-id="51933-113">Replace</span></span>|<span data-ttu-id="51933-114">在指定的输入字符串中，用指定的替换字符串来替换与正则表达式模式匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="51933-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="51933-115">IsMatch</span></span>  
 <span data-ttu-id="51933-116">如果 `IsMatch` 字符串属性在 `true` 属性中指定的正则表达式中找到匹配项，则 `Input` 自定义活动返回 `Pattern`。</span><span class="sxs-lookup"><span data-stu-id="51933-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="51933-117">该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="51933-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="51933-118">下表描述了 `IsMatch` 自定义活动的属性和返回值。</span><span class="sxs-lookup"><span data-stu-id="51933-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="51933-119">属性或返回值</span><span class="sxs-lookup"><span data-stu-id="51933-119">Property or Return Value</span></span>|<span data-ttu-id="51933-120">描述</span><span class="sxs-lookup"><span data-stu-id="51933-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="51933-121">Pattern（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-121">Pattern (required)</span></span>|<span data-ttu-id="51933-122">用于搜索的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="51933-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="51933-123">Input（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-123">Input (required)</span></span>|<span data-ttu-id="51933-124">要搜索的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-124">The input string to search.</span></span>|  
|<span data-ttu-id="51933-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="51933-125">RegexOptions</span></span>|<span data-ttu-id="51933-126">按位 OR 组合[RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446)枚举值。</span><span class="sxs-lookup"><span data-stu-id="51933-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="51933-127">返回值</span><span class="sxs-lookup"><span data-stu-id="51933-127">Return value</span></span>|<span data-ttu-id="51933-128">如果输入找到了符合所提供的模式的匹配项，则为 `true`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="51933-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="51933-129">下面的代码示例演示如何使用 `IsMatch` 自定义活动。</span><span class="sxs-lookup"><span data-stu-id="51933-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="51933-130">匹配</span><span class="sxs-lookup"><span data-stu-id="51933-130">Matches</span></span>  
 <span data-ttu-id="51933-131">`Matches` 自定义活动在输入字符串中搜索所有正则表达式，然后返回所有成功的匹配项。</span><span class="sxs-lookup"><span data-stu-id="51933-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="51933-132">该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="51933-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="51933-133">下表描述了 `IsMatch` 自定义活动的属性和返回值。</span><span class="sxs-lookup"><span data-stu-id="51933-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="51933-134">属性或返回值</span><span class="sxs-lookup"><span data-stu-id="51933-134">Property or Return Value</span></span>|<span data-ttu-id="51933-135">描述</span><span class="sxs-lookup"><span data-stu-id="51933-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="51933-136">Pattern（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-136">Pattern (required)</span></span>|<span data-ttu-id="51933-137">用于搜索的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="51933-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="51933-138">Input（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-138">Input (required)</span></span>|<span data-ttu-id="51933-139">要搜索的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-139">The input string to search.</span></span>|  
|<span data-ttu-id="51933-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="51933-140">RegexOptions</span></span>|<span data-ttu-id="51933-141">按位 OR 组合[RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446)枚举值。</span><span class="sxs-lookup"><span data-stu-id="51933-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="51933-142">返回值</span><span class="sxs-lookup"><span data-stu-id="51933-142">Return Value</span></span>|<span data-ttu-id="51933-143">一个包含成功匹配项的集合的 <xref:System.Text.RegularExpressions.MatchCollection>。</span><span class="sxs-lookup"><span data-stu-id="51933-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="51933-144">下面的代码示例演示如何使用 `Matches` 自定义活动。</span><span class="sxs-lookup"><span data-stu-id="51933-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="51933-145">替换</span><span class="sxs-lookup"><span data-stu-id="51933-145">Replace</span></span>  
 <span data-ttu-id="51933-146">`Replace` 自定义活动搜索输入字符串，然后用一个字符串来替换与指定的正则表达式匹配的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="51933-147">该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="51933-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="51933-148">下表描述了 `Replace` 自定义活动的属性和返回值。</span><span class="sxs-lookup"><span data-stu-id="51933-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="51933-149">属性或返回值</span><span class="sxs-lookup"><span data-stu-id="51933-149">Property or Return Value</span></span>|<span data-ttu-id="51933-150">描述</span><span class="sxs-lookup"><span data-stu-id="51933-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="51933-151">Pattern（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-151">Pattern (required)</span></span>|<span data-ttu-id="51933-152">用于搜索的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="51933-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="51933-153">Input（必需）</span><span class="sxs-lookup"><span data-stu-id="51933-153">Input (required)</span></span>|<span data-ttu-id="51933-154">要搜索的输入字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-154">The input string to search.</span></span>|  
|<span data-ttu-id="51933-155">Replacement</span><span class="sxs-lookup"><span data-stu-id="51933-155">Replacement</span></span>|<span data-ttu-id="51933-156">替换字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="51933-157">如果指定 `Replacement`，则将忽略 `MatchEvaluator` 属性。</span><span class="sxs-lookup"><span data-stu-id="51933-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="51933-158">必须设置 `Replacement` 或 `MatchEvaluator` 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="51933-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="51933-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="51933-159">MatchEvaluator</span></span>|<span data-ttu-id="51933-160">一个自定义方法，该方法检查每个匹配项，然后返回原始的匹配字符串或替换字符串。</span><span class="sxs-lookup"><span data-stu-id="51933-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="51933-161">如果指定 `Replacement`，则将忽略 `MatchEvaluator` 属性。</span><span class="sxs-lookup"><span data-stu-id="51933-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="51933-162">必须设置 `Replacement` 或 `MatchEvaluator` 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="51933-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="51933-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="51933-163">RegexOptions</span></span>|<span data-ttu-id="51933-164">按位 OR 组合[RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446)枚举值。</span><span class="sxs-lookup"><span data-stu-id="51933-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="51933-165">返回值</span><span class="sxs-lookup"><span data-stu-id="51933-165">Return Value</span></span>|<span data-ttu-id="51933-166">一个包含成功匹配项的集合的 <xref:System.Text.RegularExpressions.MatchCollection>。</span><span class="sxs-lookup"><span data-stu-id="51933-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="51933-167">下面的代码示例演示如何使用 `Replace` 自定义活动。</span><span class="sxs-lookup"><span data-stu-id="51933-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="51933-168">使用此示例</span><span class="sxs-lookup"><span data-stu-id="51933-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="51933-169">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 RegexActivities.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="51933-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="51933-170">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="51933-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="51933-171">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="51933-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51933-172">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="51933-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51933-173">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="51933-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="51933-174">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="51933-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51933-175">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="51933-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`  
  
## <a name="see-also"></a><span data-ttu-id="51933-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51933-176">See Also</span></span>
