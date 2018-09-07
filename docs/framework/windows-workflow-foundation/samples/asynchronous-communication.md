---
title: 异步通信
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e85f7efb0de1326ceb5091c305b20f34809eab57
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44047082"
---
# <a name="asynchronous-communication"></a>异步通信
此示例演示如何两个不同的 Windows Workflow Foundation (WF) 服务之间的通信默认情况下以异步方式完成。  
  
## <a name="demonstrates"></a>演示  
 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 服务间的异步通信。  
  
## <a name="discussion"></a>讨论  
 此示例演示如何使用 .NET Framework 提供的消息传递活动来异步执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 应用程序间的通信。  
  
 此示例包含以下三个项目。  
  
 CreditCheckService  
 此服务接收特定人员的信用评分或要购买的商品的价值，然后决定是否为该人员提供贷款。  
  
 RentalApprovalService  
 此服务接收来自需要贷款的人员的申请。 此服务与 `CreditCheckService` 进行异步通信以决定贷款申请是否有效。  
  
 客户端  
 此客户端与 `RentalApprovalService` 进行同步通信以了解是否已批准贷款。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  右键单击**AsynchronousCommunication**解决方案并选择**属性**。  
  
2.  在**常见属性**，选择**启动项目**，然后选择**多个启动项目**。  
  
3.  移动**RentalApprovalService**列表中的第一个位置后, 接**CreditCheckService**后, 跟**客户端**。 设置**启动**上所有三个项目的操作。  
  
4.  单击**确定**，然后按 F5 以运行示例。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
