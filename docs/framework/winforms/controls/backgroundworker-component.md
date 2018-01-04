---
title: "BackgroundWorker 组件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d83ff69053a71626d0bf9a844d9e94235080d78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="backgroundworker-component"></a>BackgroundWorker 组件
`BackgroundWorker`组件使你的窗体或控件异步运行操作。  
  
## <a name="in-this-section"></a>本节内容  
 [BackgroundWorker 组件概述](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 描述`BackgroundWorker`组件，这将使您能够执行耗时的操作以异步方式 （"在后台"），不同于你的应用程序的主 UI 线程的线程上。  
  
 [演练：在后台运行操作](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 演示如何使用`BackgroundWorker`组件在设计器中运行单独的线程上耗时的操作。  
  
 [如何：在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 演示如何使用`BackgroundWorker`组件以运行在单独线程上耗时的操作。  
  
 [演练：实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 创建应用程序使用的设计器以异步方式执行数学运算。  
  
 [如何：实现使用后台操作的窗体](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 创建的应用程序以异步方式执行数学运算。  
  
 [如何：在后台下载文件](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 演示如何使用`BackgroundWorker`组件要下载在单独线程上的文件。  
  
## <a name="reference"></a>参考  
 <xref:System.ComponentModel.BackgroundWorker>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 描述保存数据的类型<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 描述保存数据的类型<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件。  
  
## <a name="related-sections"></a>相关章节  
 [基于事件的异步模式概述](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 描述如何的异步模式提供多线程应用程序的优点同时隐藏了很多线程设计中固有的复杂问题。
