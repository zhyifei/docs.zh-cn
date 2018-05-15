---
title: 自定义补偿示例
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c4d7219a2f16091d1997de6186312cce5ece0bd1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="89518-102">自定义补偿示例</span><span class="sxs-lookup"><span data-stu-id="89518-102">Custom Compensation Sample</span></span>
<span data-ttu-id="89518-103">此示例演示如何使用 <xref:System.Activities.Statements.CompensableActivity> 及其补偿处理程序以定义自定义补偿逻辑。</span><span class="sxs-lookup"><span data-stu-id="89518-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="89518-104">此示例中已建模的方案为“卡车租赁公司”。</span><span class="sxs-lookup"><span data-stu-id="89518-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="89518-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="89518-105">Sample Details</span></span>  
 <span data-ttu-id="89518-106">模拟的步骤为：</span><span class="sxs-lookup"><span data-stu-id="89518-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="89518-107">用户向卡车租赁商询问给定日期内的报价。</span><span class="sxs-lookup"><span data-stu-id="89518-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="89518-108">联系三家卡车公司，这三家公司提供了三份报价。</span><span class="sxs-lookup"><span data-stu-id="89518-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="89518-109">用户选择一份卡车报价，并通过信用卡来进行订购。</span><span class="sxs-lookup"><span data-stu-id="89518-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="89518-110">应用程序取消了其他两份卡车报价。</span><span class="sxs-lookup"><span data-stu-id="89518-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="89518-111">如果在预订日期的前 10 天内取消预订，则应用程序将收取一定的服务费，对于非高级帐户而言，此服务费是不可退还的。</span><span class="sxs-lookup"><span data-stu-id="89518-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="89518-112">应用程序收取卡车租赁费。</span><span class="sxs-lookup"><span data-stu-id="89518-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="89518-113">在预订日期之前或客户决定取消预订之前（以二者中较早的日期为准），应用程序将一直等待。</span><span class="sxs-lookup"><span data-stu-id="89518-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="89518-114">如果客户取消预订，则 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 自定义补偿逻辑将按照以下逻辑运行：</span><span class="sxs-lookup"><span data-stu-id="89518-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="89518-115">如果客户拥有非高级帐户且取消操作发生在预订日期前的 10 天内，则仍将收取服务费；否则，应用程序将退还服务费。</span><span class="sxs-lookup"><span data-stu-id="89518-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="89518-116">其他可补偿的活动（卡车订购 + 卡车订购费）将根据默认补偿逻辑运行，这将按相反的执行顺序进行补偿。</span><span class="sxs-lookup"><span data-stu-id="89518-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="89518-117">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="89518-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="89518-118">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 CustomCompensation.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="89518-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="89518-119">它位于 \WF\Basic\Compensation\CustomCompensation 目录中。</span><span class="sxs-lookup"><span data-stu-id="89518-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="89518-120">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="89518-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="89518-121">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="89518-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89518-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="89518-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="89518-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="89518-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="89518-124">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="89518-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="89518-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="89518-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`