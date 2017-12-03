---
title: "对服务操作失败进行监视"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6030b1ad1dc3953137d3b068be1bceb99975a5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="monitoring-service-operation-failures"></a>对服务操作失败进行监视
如果为应用程序启用了分析跟踪，则可以在事件查看器中轻松地监视服务失败。  本主题演示如何确定服务操作失败的时间，以及如何确定失败的原因。  
  
### <a name="determining-service-operation-failure-information"></a>确定服务操作失败信息  
  
1.  通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。  
  
2.  如果尚未启用分析跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**. 选择**视图**，**显示分析和调试日志**。 右键单击**分析**和选择**启用日志**。 保持事件查看器打开，以便在服务操作失败后可以查看跟踪。  
  
3.  接下来，打开在中创建的示例[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)中[!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]请注意，必须运行[!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]以管理员身份，以便可以创建服务。 如果你有[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]安装的示例，你可以打开[入门](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含已完成本教程中创建的项目。  
  
4.  在服务器项目的 Program.cs 文件中，将以下代码行添加到 `Divide` 类中 `CalculatorService` 方法的开头：  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  在客户端项目的 Program.cs 文件中，将分配给 value2 的值更改为零：  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  执行服务器应用程序而不进行调试按**Ctrl + F5**。  
  
7.  打开 Visual Studio 命令提示。  定位到客户端目录，然后从命令行执行该客户端。  
  
8.  在事件查看器中，禁用并刷新分析日志，然后按事件 ID 对事件排序。  查找具有事件 ID 的事件[219-ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md)，用于描述服务失败。  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  事件在发送到事件查看器时将被缓冲；可能不会立即显示失败事件。
