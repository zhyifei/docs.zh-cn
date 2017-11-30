---
title: "使用过程性活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="b9205-102">使用过程性活动</span><span class="sxs-lookup"><span data-stu-id="b9205-102">Using Procedural Activities</span></span>
<span data-ttu-id="b9205-103">此示例使用 <xref:System.Activities.Statements.Sequence>、<xref:System.Activities.Statements.Assign>、<xref:System.Activities.Statements.If>、<xref:System.Activities.Statements.While>、<xref:System.Activities.Statements.Switch%601>、<xref:System.Activities.Statements.TryCatch> 和 <xref:System.Activities.Statements.WriteLine> 活动实现猜谜游戏。</span><span class="sxs-lookup"><span data-stu-id="b9205-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="b9205-104">猜谜游戏将选择一个随机数，然后玩家必须猜出该数字。</span><span class="sxs-lookup"><span data-stu-id="b9205-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="b9205-105">当玩家所猜测的数字错误时，工作流会给出一个提示，指示所猜的数字是过大还是过小。</span><span class="sxs-lookup"><span data-stu-id="b9205-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="b9205-106">如果玩家在 7 次之内猜出该数字，则将为其显示特定的祝贺语。</span><span class="sxs-lookup"><span data-stu-id="b9205-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="b9205-107">此示例中的自定义活动</span><span class="sxs-lookup"><span data-stu-id="b9205-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="b9205-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="b9205-108">ReadLine</span></span>  
 <span data-ttu-id="b9205-109">从控制台读取一行文本。</span><span class="sxs-lookup"><span data-stu-id="b9205-109">Reads a line of text from the console.</span></span> <span data-ttu-id="b9205-110">此活动派生自 <xref:System.Activities.NativeActivity> 类，并创建一个书签，控制台应用程序在读取行时将恢复该书签。</span><span class="sxs-lookup"><span data-stu-id="b9205-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="b9205-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="b9205-111">PromptInt</span></span>  
 <span data-ttu-id="b9205-112">提示用户键入一个数字，然后从控制台窗口读取该数字。</span><span class="sxs-lookup"><span data-stu-id="b9205-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="b9205-113">此活动派生自 <xref:System.Activities.Activity%601> 并使用 <xref:System.Activities.Statements.WriteLine> 和 `ReadLine` 活动。</span><span class="sxs-lookup"><span data-stu-id="b9205-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="b9205-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="b9205-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="b9205-115">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 GuessingGame.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b9205-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b9205-116">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="b9205-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b9205-117">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="b9205-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9205-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b9205-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9205-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b9205-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b9205-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="b9205-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9205-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b9205-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a><span data-ttu-id="b9205-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9205-122">See Also</span></span>
