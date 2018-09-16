---
title: 正则表达式活动
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668946"
---
# <a name="regular-expression-activities"></a>正则表达式活动
此示例演示如何一组活动，这些活动公开 <xref:System.Text.RegularExpressions> 命名空间的正则表达式功能。 这些自定义活动可以在工作流应用程序中使用。 有关正则表达式的详细信息，请参阅[更多信息](https://go.microsoft.com/fwlink/?LinkId=150434)Namespace。  
  
 下表详细介绍了此示例中的自定义活动。  
  
|Activity|描述|  
|--------------|-----------------|  
|IsMatch|指定正则表达式是否在输入字符串中找到了匹配项。|  
|匹配|在输入字符串中搜索所有正则表达式，然后返回所有成功的匹配项。|  
|替换|在指定的输入字符串中，用指定的替换字符串来替换与正则表达式模式匹配的字符串。|  
  
## <a name="ismatch"></a>IsMatch  
 如果 `IsMatch` 字符串属性在 `true` 属性中指定的正则表达式中找到匹配项，则 `Input` 自定义活动返回 `Pattern`。 该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 方法。  
  
 下表描述了 `IsMatch` 自定义活动的属性和返回值。  
  
|属性或返回值|描述|  
|------------------------------|-----------------|  
|Pattern（必需）|用于搜索的正则表达式。|  
|Input（必需）|要搜索的输入字符串。|  
|RegexOptions|按位 OR 组合[RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446)枚举值。|  
|返回值|如果输入找到了符合所提供的模式的匹配项，则为 `true`；否则为 `false`。|  
  
 下面的代码示例演示如何使用 `IsMatch` 自定义活动。  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a>匹配  
 `Matches` 自定义活动在输入字符串中搜索所有正则表达式，然后返回所有成功的匹配项。 该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 方法。  
  
 下表描述了 `IsMatch` 自定义活动的属性和返回值。  
  
|属性或返回值|描述|  
|------------------------------|-----------------|  
|Pattern（必需）|用于搜索的正则表达式。|  
|Input（必需）|要搜索的输入字符串。|  
|RegexOptions|按位 OR 组合[RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446)枚举值。|  
|返回值|一个包含成功匹配项的集合的 <xref:System.Text.RegularExpressions.MatchCollection>。|  
  
 下面的代码示例演示如何使用 `Matches` 自定义活动。  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a>替换  
 `Replace` 自定义活动搜索输入字符串，然后用一个字符串来替换与指定的正则表达式匹配的所有字符串。 该活动派生自 <xref:System.Activities.CodeActivity%601>，并在 <xref:System.Activities.CodeActivity%601.Execute%2A> 方法中调用 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 方法。  
  
 下表描述了 `Replace` 自定义活动的属性和返回值。  
  
|属性或返回值|描述|  
|------------------------------|-----------------|  
|Pattern（必需）|用于搜索的正则表达式。|  
|Input（必需）|要搜索的输入字符串。|  
|Replacement|替换字符串。<br /><br /> 如果指定 `Replacement`，则将忽略 `MatchEvaluator` 属性。 必须设置 `Replacement` 或 `MatchEvaluator` 属性中的一个。|  
|MatchEvaluator|一个自定义方法，该方法检查每个匹配项，然后返回原始的匹配字符串或替换字符串。<br /><br /> 如果指定 `Replacement`，则将忽略 `MatchEvaluator` 属性。 必须设置 `Replacement` 或 `MatchEvaluator` 属性中的一个。|  
|RegexOptions|按位 OR 组合[RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446)枚举值。|  
|返回值|一个包含成功匹配项的集合的 <xref:System.Text.RegularExpressions.MatchCollection>。|  
  
 下面的代码示例演示如何使用 `Replace` 自定义活动。  
  
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
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 RegexActivities.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`