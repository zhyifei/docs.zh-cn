---
title: 自定义跟踪记录
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: d4733b4ffc0d866cf90fd5a5e7d649de261c45fb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499116"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="d4373-102">自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="d4373-102">Custom Tracking Records</span></span>

<span data-ttu-id="d4373-103">本主题演示如何创建自定义跟踪记录并在这些记录中填入将与其一起发出的数据。</span><span class="sxs-lookup"><span data-stu-id="d4373-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="d4373-104">发出自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="d4373-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="d4373-105">可以从代码活动中发出自定义跟踪记录，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d4373-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="d4373-106">通过对 <xref:System.Activities.Tracking.CustomTrackingRecord> 调用 <xref:System.Activities.NativeActivityContext.Track%2A> 方法，在代码活动中发出 `ActivityContext`。</span><span class="sxs-lookup"><span data-stu-id="d4373-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4373-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4373-107">See also</span></span>

- [<span data-ttu-id="d4373-108">Windows Server App Fabric 监视</span><span class="sxs-lookup"><span data-stu-id="d4373-108">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="d4373-109">使用 App Fabric 监视应用程序</span><span class="sxs-lookup"><span data-stu-id="d4373-109">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
