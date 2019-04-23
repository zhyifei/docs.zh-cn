---
title: 确定服务操作持续时间
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772762"
---
# <a name="determining-service-operation-duration"></a>确定服务操作持续时间
如果 Windows Communication Foundation (WCF) 应用程序中启用了分析跟踪，则可轻松地通过检查事件日志确定服务操作的执行持续时间。  本主题演示如何确定完成服务操作所需的时间量。  
  
### <a name="determining-service-operation-execution-duration"></a>确定服务操作执行持续时间  
  
1. 通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。  
  
2. 如果尚未启用分析跟踪，展开**应用程序和服务日志**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**. 选择**视图**，**显示分析和调试日志**。 右键单击**Analytic** ，然后选择**启用日志**。 保持事件查看器打开，以便在服务操作运行后可以查看跟踪。  
  
3. 接下来，打开包含一个服务项目以及与该服务交互的客户端项目的 WCF 应用程序。  可以通过创建此类应用程序[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)。  如果您有安装 WCF 示例，可以打开[Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含本教程中创建的已完成的项目。  
  
4. 按执行服务器应用程序**F5**。 通过右键单击执行客户端应用程序**客户端**项目并选择**调试**，**启动新实例**。  
  
5. 在事件查看器中，刷新分析日志，然后按事件 ID 对事件排序。  查找事件 ID 的事件[214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)。  这些事件将显示已完成的操作以及操作的持续时间。  下面的事件显示 Add 操作的持续时间。  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
