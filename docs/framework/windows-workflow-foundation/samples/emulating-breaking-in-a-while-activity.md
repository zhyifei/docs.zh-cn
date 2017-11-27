---
title: "在 While 活动中模拟中断"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4417f4225200f01f23d753f6b7aa52ebc69cab4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="7488b-102">在 While 活动中模拟中断</span><span class="sxs-lookup"><span data-stu-id="7488b-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="7488b-103">此示例演示如何中断下列活动的循环机制：<xref:System.Activities.Statements.DoWhile>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.While> 和 <xref:System.Activities.Statements.ParallelForEach%601>。</span><span class="sxs-lookup"><span data-stu-id="7488b-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="7488b-104">这样做很有用，因为 [!INCLUDE[wf](../../../../includes/wf-md.md)] 并不包括任何可中断这些循环的执行的活动。</span><span class="sxs-lookup"><span data-stu-id="7488b-104">This is useful because [!INCLUDE[wf](../../../../includes/wf-md.md)] does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="7488b-105">方案</span><span class="sxs-lookup"><span data-stu-id="7488b-105">Scenario</span></span>  
 <span data-ttu-id="7488b-106">此示例从供应商列表（`Vendor` 类的实例）中查找第一个可靠的供应商。</span><span class="sxs-lookup"><span data-stu-id="7488b-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="7488b-107">每个供应商都具有一个 `ID`、一个 `Name` 和一个用于确定供应商的可靠程度的可靠性值。</span><span class="sxs-lookup"><span data-stu-id="7488b-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="7488b-108">此示例创建一个名为 `FindReliableVendor` 的自定义活动，该活动接收两个输入参数（一个供应商列表和一个最小可靠值），然后返回列表中符合提供的条件的第一个供应商。</span><span class="sxs-lookup"><span data-stu-id="7488b-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="7488b-109">中断循环</span><span class="sxs-lookup"><span data-stu-id="7488b-109">Breaking a Loop</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="7488b-110"> 不包括用于中断循环的活动。</span><span class="sxs-lookup"><span data-stu-id="7488b-110"> does not include an activity to break a loop.</span></span> <span data-ttu-id="7488b-111">此代码示例通过使用一个 <xref:System.Activities.Statements.If> 活动和若干变量，可实现循环中断。</span><span class="sxs-lookup"><span data-stu-id="7488b-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="7488b-112">在此示例中，当为 <xref:System.Activities.Statements.While> 变量分配一个值而不是 `reliableVendor` 时，则会中断 `null` 活动。</span><span class="sxs-lookup"><span data-stu-id="7488b-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="7488b-113">以下代码示例演示了此示例如何中断一个 while 循环。</span><span class="sxs-lookup"><span data-stu-id="7488b-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7488b-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="7488b-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="7488b-115">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 EmulatingBreakInWhile.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7488b-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7488b-116">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="7488b-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7488b-117">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="7488b-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7488b-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7488b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7488b-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7488b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7488b-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="7488b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7488b-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7488b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`  
  
## <a name="see-also"></a><span data-ttu-id="7488b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7488b-122">See Also</span></span>
