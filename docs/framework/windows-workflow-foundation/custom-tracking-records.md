---
title: 自定义跟踪记录
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 986f0350c24414d0ff960474445adf6ac3f39734
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802617"
---
# <a name="custom-tracking-records"></a>自定义跟踪记录

本主题演示如何创建自定义跟踪记录并在这些记录中填入将与其一起发出的数据。

## <a name="emitting-custom-tracking-records"></a>发出自定义跟踪记录

可以从代码活动中发出自定义跟踪记录，如下面的示例所示。

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

通过对 <xref:System.Activities.Tracking.CustomTrackingRecord> 调用 <xref:System.Activities.NativeActivityContext.Track%2A> 方法，在代码活动中发出 `ActivityContext`。

## <a name="see-also"></a>另请参阅

- [Windows Server App Fabric 监视](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [用 App Fabric 监视应用程序](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
