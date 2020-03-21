---
title: 异步通信
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e1bc63b5d3178b8e98350dedd8eb0791e0e35589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142871"
---
# <a name="asynchronous-communication"></a>异步通信
此示例演示如何在默认情况下异步地完成两个不同的 Windows 工作流基础 （WF） 服务之间的通信。  
  
## <a name="demonstrates"></a>演示  
 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 服务间的异步通信。  
  
## <a name="discussion"></a>讨论区  
 此示例演示如何使用 .NET Framework 提供的消息传递活动来异步执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 应用程序间的通信。  
  
 此示例包含以下三个项目。  
  
 CreditCheckService  
 此服务接收特定人员的信用评分或要购买的商品的价值，然后决定是否为该人员提供贷款。  
  
 RentalApprovalService  
 此服务接收来自需要贷款的人员的申请。 此服务与 `CreditCheckService` 进行异步通信以决定贷款申请是否有效。  
  
 Client  
 此客户端与 `RentalApprovalService` 进行同步通信以了解是否已批准贷款。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 右键单击**异步通信**解决方案并选择**属性**。  
  
2. 在 **"通用属性**"中，选择**启动项目**，然后选择**多个启动项目**。  
  
3. 将**租赁批准服务**移到列表中的第一个位置，后跟**CreditCheck 服务**，后跟**客户**。 为所有三个项目设置 **"开始"** 操作。  
  
4. 单击 **"确定**"，然后按 F5 以运行示例。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
