---
title: 可补偿活动示例
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 3bf1d120cd700830a98f53495f7e9989ffec73db
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44263590"
---
# <a name="compensable-activity-sample"></a>可补偿活动示例
此示例演示如何使用 `CompensableActivity` 活动来定义在正常执行过程中要为某个给定操作完成的工作，以及为补偿该操作而需完成的工作（如果稍后需要这样做）。  该示例的第一部分演示如何补偿工作的单元可以定义为 Windows Workflow Foundation (WF) 中使用`CompensableActivity`活动，并在成功运行的执行。  此示例的第二部分演示在遇到意外事件和取消工作流实例时，相同单元数量的可补偿工作如何自动负责补偿。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用 Visual Studio 2010 打开 CompensableActivity.sln。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  按 F5 运行应用程序。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`