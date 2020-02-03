---
title: 控件中的多线程处理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742142"
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows 窗体控件中的多线程处理
在许多应用程序中，你可以通过在另一个线程上执行耗时的操作，使你的用户界面（UI）更快地响应。 许多工具可用于多线程处理 Windows 窗体控件，包括 <xref:System.Threading> 命名空间、<xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 方法和 `BackgroundWorker` 组件。  
  
> [!NOTE]
> `BackgroundWorker` 组件将替换功能并将其添加到 <xref:System.Threading> 命名空间和 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 方法;但是，如果您选择，这些将保留以实现向后兼容性和将来使用。 有关详细信息，请参阅[BackgroundWorker 组件概述](backgroundworker-component-overview.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：对 Windows 窗体控件执行线程安全调用](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 演示如何对 Windows 窗体控件进行线程安全的调用。  
  
 [如何：使用后台线程搜索文件](how-to-use-a-background-thread-to-search-for-files.md)  
 演示如何使用 <xref:System.Threading> 命名空间和 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 方法以异步方式搜索文件。  
  
## <a name="reference"></a>参考  
 <xref:System.ComponentModel.BackgroundWorker>  
 记录一个组件，该组件封装用于异步操作的工作线程。  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 记录如何以异步方式加载声音。  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 记录如何以异步方式加载图像。  
  
## <a name="related-sections"></a>相关章节  
 [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)  
 演示如何使用 <xref:System.ComponentModel.BackgroundWorker> 组件执行耗时的操作。  
  
 [BackgroundWorker 组件概述](backgroundworker-component-overview.md)  
 提供一些主题，这些主题介绍如何使用 <xref:System.ComponentModel.BackgroundWorker> 组件进行异步操作。
