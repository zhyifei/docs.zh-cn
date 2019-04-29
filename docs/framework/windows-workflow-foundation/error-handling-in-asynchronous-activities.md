---
title: 异步活动中的错误处理
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 4a7cbecef596eec6eaa128b8ffc7bc5c6e4b79bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773992"
---
# <a name="error-handling-in-asynchronous-activities"></a>异步活动中的错误处理
在 <xref:System.Activities.AsyncCodeActivity> 中提供错误处理涉及通过活动的回调系统传输错误。 本主题介绍如何使用 SendMail 活动示例，使在异步操作中引发的错误返回到主机。  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>将在异步活动中引发的错误返回到主机  
 在 SendMail 活动示例中将异步操作中的错误传输回主机涉及以下步骤：  
  
- 将 Exception 属性添加到 `SendMailAsyncResult` 类。  
  
- 将引发的错误复制到 `SendCompleted` 事件处理程序中的该属性。  
  
- 在 `EndExecute` 事件处理程序中引发异常。  
  
 最终生成的代码如下所示。  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }   
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;   
        }  
    }  
```
