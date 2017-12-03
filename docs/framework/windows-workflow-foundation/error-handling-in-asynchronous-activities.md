---
title: "异步活动中的错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7c23dec2f92ed8654d5f0460966dc19af0a8405
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="47154-102">异步活动中的错误处理</span><span class="sxs-lookup"><span data-stu-id="47154-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="47154-103">在 <xref:System.Activities.AsyncCodeActivity> 中提供错误处理涉及通过活动的回调系统传输错误。</span><span class="sxs-lookup"><span data-stu-id="47154-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="47154-104">本主题介绍如何使用 SendMail 活动示例，使在异步操作中引发的错误返回到主机。</span><span class="sxs-lookup"><span data-stu-id="47154-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="47154-105">将在异步活动中引发的错误返回到主机</span><span class="sxs-lookup"><span data-stu-id="47154-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="47154-106">在 SendMail 活动示例中将异步操作中的错误传输回主机涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="47154-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="47154-107">将 Exception 属性添加到 `SendMailAsyncResult` 类。</span><span class="sxs-lookup"><span data-stu-id="47154-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="47154-108">将引发的错误复制到 `SendCompleted` 事件处理程序中的该属性。</span><span class="sxs-lookup"><span data-stu-id="47154-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="47154-109">在 `EndExecute` 事件处理程序中引发异常。</span><span class="sxs-lookup"><span data-stu-id="47154-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="47154-110">最终生成的代码如下所示。</span><span class="sxs-lookup"><span data-stu-id="47154-110">The resulting code is as follows.</span></span>  
  
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
