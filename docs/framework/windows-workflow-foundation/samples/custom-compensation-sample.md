---
title: 自定义补偿示例
ms.date: 03/30/2017
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
ms.openlocfilehash: ac141a48f87f5b14f6b528f7b3ceb7fdddeaf2d2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503714"
---
# <a name="custom-compensation-sample"></a>自定义补偿示例
此示例演示如何使用 <xref:System.Activities.Statements.CompensableActivity> 及其补偿处理程序以定义自定义补偿逻辑。 此示例中已建模的方案为“卡车租赁公司”。  
  
## <a name="sample-details"></a>示例详细信息  
 模拟的步骤为：  
  
1.  用户向卡车租赁商询问给定日期内的报价。  
  
2.  联系三家卡车公司，这三家公司提供了三份报价。  
  
3.  用户选择一份卡车报价，并通过信用卡来进行订购。  
  
4.  应用程序取消了其他两份卡车报价。  
  
5.  如果在预订日期的前 10 天内取消预订，则应用程序将收取一定的服务费，对于非高级帐户而言，此服务费是不可退还的。  
  
6.  应用程序收取卡车租赁费。  
  
7.  在预订日期之前或客户决定取消预订之前（以二者中较早的日期为准），应用程序将一直等待。  
  
8.  如果客户取消预订，则 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 自定义补偿逻辑将按照以下逻辑运行：  
  
    1.  如果客户拥有非高级帐户且取消操作发生在预订日期前的 10 天内，则仍将收取服务费；否则，应用程序将退还服务费。  
  
    2.  其他可补偿的活动（卡车订购 + 卡车订购费）将根据默认补偿逻辑运行，这将按相反的执行顺序进行补偿。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，打开 CustomCompensation.sln 解决方案。 它位于 \WF\Basic\Compensation\CustomCompensation 目录中。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  按 Ctrl+F5 运行应用程序。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`