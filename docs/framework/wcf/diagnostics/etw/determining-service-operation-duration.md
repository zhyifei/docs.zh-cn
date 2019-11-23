---
title: 确定服务操作持续时间
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 06a4c2da7b702fa4fbc1469576c118b790803339
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291419"
---
# <a name="determining-service-operation-duration"></a>确定服务操作持续时间
如果在 Windows Communication Foundation （WCF）应用程序中启用了分析跟踪，则可以通过检查事件日志轻松确定服务操作的执行持续时间。  本主题演示如何确定完成服务操作所需的时间量。  
  
### <a name="determining-service-operation-execution-duration"></a>确定服务操作执行持续时间  
  
1. 通过单击 "**开始**"、"**运行**"，然后输入 `eventvwr.exe`打开事件查看器。  
  
2. 如果尚未启用分析跟踪，请展开 "**应用程序和服务日志**"、" **Microsoft**"、" **Windows**"、"**应用程序服务器应用程序**"。 选择 "**查看**"、"**显示分析和调试日志**"。 右键单击 "**分析**"，然后选择 "**启用日志**"。 保持事件查看器打开，以便在服务操作运行后可以查看跟踪。  
  
3. 接下来，打开一个包含服务项目的 WCF 应用程序以及与该服务交互的客户端项目。  可以按照[入门教程](../../getting-started-tutorial.md)创建此类应用程序。  如果已安装 WCF 示例，则可以打开 "[入门](../../samples/getting-started-sample.md)"，其中包含本教程中创建的已完成项目。  
  
4. 按**F5**执行服务器应用程序。 右键单击**客户端**项目，然后选择 "**调试**"、"**启动新实例**" 来执行客户端应用程序。  
  
5. 在事件查看器中，刷新分析日志，然后按事件 ID 对事件排序。  查找事件 ID 为[214-OperationCompleted](214-operationcompleted.md)的事件。  这些事件将显示已完成的操作以及操作的持续时间。  下面的事件显示 Add 操作的持续时间。  
  
    ```output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
