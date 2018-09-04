---
title: RangeEnumeration 活动
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556287"
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="95f63-102">RangeEnumeration 活动</span><span class="sxs-lookup"><span data-stu-id="95f63-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="95f63-103">此示例演示如何创建一个用于循环访问数字集合的自定义活动。下表详细描述了此示例中包含的主要文件。</span><span class="sxs-lookup"><span data-stu-id="95f63-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="95f63-104">文件名</span><span class="sxs-lookup"><span data-stu-id="95f63-104">File name</span></span>|<span data-ttu-id="95f63-105">描述</span><span class="sxs-lookup"><span data-stu-id="95f63-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95f63-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="95f63-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="95f63-107">定义一个名为 `RangeEnumeration` 的自定义活动，该活动重写 <xref:System.Activities.NativeActivity> 类，并循环访问一系列数字。</span><span class="sxs-lookup"><span data-stu-id="95f63-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="95f63-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="95f63-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="95f63-109">一个使用 `RangeEnumeration` 活动循环访问数字集合的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="95f63-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="95f63-110">下表详细描述了 `RangeEnumeration` 活动的属性。</span><span class="sxs-lookup"><span data-stu-id="95f63-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="95f63-111">属性</span><span class="sxs-lookup"><span data-stu-id="95f63-111">Property</span></span>|<span data-ttu-id="95f63-112">描述</span><span class="sxs-lookup"><span data-stu-id="95f63-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="95f63-113">Start</span><span class="sxs-lookup"><span data-stu-id="95f63-113">Start</span></span>|<span data-ttu-id="95f63-114">开始循环的整数。</span><span class="sxs-lookup"><span data-stu-id="95f63-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="95f63-115">停止</span><span class="sxs-lookup"><span data-stu-id="95f63-115">Stop</span></span>|<span data-ttu-id="95f63-116">停止循环的整数。</span><span class="sxs-lookup"><span data-stu-id="95f63-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="95f63-117">步骤</span><span class="sxs-lookup"><span data-stu-id="95f63-117">Step</span></span>|<span data-ttu-id="95f63-118">指定每次循环访问的步长。</span><span class="sxs-lookup"><span data-stu-id="95f63-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="95f63-119">Body</span><span class="sxs-lookup"><span data-stu-id="95f63-119">Body</span></span>|<span data-ttu-id="95f63-120">指定每次循环访问期间要执行的代码。</span><span class="sxs-lookup"><span data-stu-id="95f63-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="95f63-121">使用此示例</span><span class="sxs-lookup"><span data-stu-id="95f63-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="95f63-122">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 RangeEnumeration.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="95f63-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="95f63-123">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="95f63-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="95f63-124">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="95f63-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="95f63-125">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="95f63-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="95f63-126">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="95f63-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="95f63-127">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="95f63-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="95f63-128">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="95f63-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`