---
title: "确定服务操作持续时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24f1bc22e088c0198ec8a8f8183611d2b43941b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="determining-service-operation-duration"></a>确定服务操作持续时间
如果在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 应用程序中启用了分析跟踪，则通过检查事件日志可方便地确定服务操作的执行持续时间。  本主题演示如何确定完成服务操作所需的时间量。  
  
### <a name="determining-service-operation-execution-duration"></a>确定服务操作执行持续时间  
  
1.  通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。  
  
2.  如果尚未启用分析跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**. 选择**视图**，**显示分析和调试日志**。 右键单击**分析**和选择**启用日志**。 保持事件查看器打开，以便在服务操作运行后可以查看跟踪。  
  
3.  接下来，打开 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 应用程序，其中包含一个服务项目以及一个与该服务交互的客户端项目。  你可以创建这样的应用程序按照[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)。  如果你有[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]安装的示例，你可以打开[入门](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含已完成本教程中创建的项目。  
  
4.  通过按执行服务器应用程序**F5**。 通过右键单击执行客户端应用程序**客户端**项目并选择**调试**，**启动新实例**。  
  
5.  在事件查看器中，刷新分析日志，然后按事件 ID 对事件排序。  查找事件 id [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)。  这些事件将显示已完成的操作以及操作的持续时间。  下面的事件显示 Add 操作的持续时间。  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
