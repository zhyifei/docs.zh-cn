---
title: "自定义跟踪记录"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a459e6df0e030f4e17bb73461d8fa790a61787e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="custom-tracking-records"></a><span data-ttu-id="b3c3f-102">自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="b3c3f-102">Custom Tracking Records</span></span>
<span data-ttu-id="b3c3f-103">本主题演示如何创建自定义跟踪记录并在这些记录中填入将与其一起发出的数据。</span><span class="sxs-lookup"><span data-stu-id="b3c3f-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>  
  
## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="b3c3f-104">发出自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="b3c3f-104">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="b3c3f-105">可以从代码活动中发出自定义跟踪记录，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b3c3f-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <span data-ttu-id="b3c3f-106">通过对 <xref:System.Activities.Tracking.CustomTrackingRecord> 调用 <xref:System.Activities.NativeActivityContext.Track%2A> 方法，在代码活动中发出 `ActvityContext`。</span><span class="sxs-lookup"><span data-stu-id="b3c3f-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActvityContext`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c3f-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3c3f-107">See Also</span></span>  
 [<span data-ttu-id="b3c3f-108">Windows Server App Fabric 监视</span><span class="sxs-lookup"><span data-stu-id="b3c3f-108">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="b3c3f-109">使用 App Fabric 监视应用程序</span><span class="sxs-lookup"><span data-stu-id="b3c3f-109">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
