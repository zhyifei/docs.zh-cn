---
title: Windows 窗体控件中的多线程处理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 68822c62a1a195ce3128d51c765cfeba2056955d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536352"
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows 窗体控件中的多线程处理
在许多应用程序，你可以进行用户界面 (UI) 更快地响应执行耗时的操作在另一个线程上。 有多种工具都是可用于多线程处理你的 Windows 窗体控件，包括<xref:System.Threading>命名空间，<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>方法，与`BackgroundWorker`组件。  
  
> [!NOTE]
>  `BackgroundWorker`组件替换，并添加了功能<xref:System.Threading>命名空间和<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>方法; 但是，这些会保留向后兼容性和将来使用，如果你选择。 有关详细信息，请参阅[BackgroundWorker 组件概述](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：对 Windows 窗体控件执行线程安全调用](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 演示如何使 Windows 窗体控件的线程安全调用。  
  
 [如何：使用后台线程搜索文件](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 演示如何使用<xref:System.Threading>命名空间和<xref:System.Windows.Forms.Control.BeginInvoke%2A>方法来以异步方式搜索文件。  
  
## <a name="reference"></a>参考  
 <xref:System.ComponentModel.BackgroundWorker>  
 记录封装工作线程为异步操作的组件。  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 介绍如何异步加载声音。  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 介绍如何以异步方式加载映像。  
  
## <a name="related-sections"></a>相关章节  
 [如何：在后台运行操作](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 演示如何执行耗时的操作与<xref:System.ComponentModel.BackgroundWorker>组件。  
  
 [BackgroundWorker 组件概述](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 提供一些主题，介绍如何使用<xref:System.ComponentModel.BackgroundWorker>组件为异步操作。
