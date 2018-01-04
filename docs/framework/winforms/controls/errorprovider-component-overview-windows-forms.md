---
title: "ErrorProvider 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 组件概述（Windows 窗体）
Windows 窗体[ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md)组件用来验证窗体或控件上的用户输入。 它通常是与验证窗体上的用户输入或显示在数据集中的错误结合使用。 错误提供程序是更好的选择，比在消息框中，显示一条错误消息，因为后关闭消息框，则错误消息不再可见。 <xref:System.Windows.Forms.ErrorProvider>组件显示错误图标 (![ErrorProvider 图标](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) 相关的控件，如文本框; 当用户鼠标指针悬停旁边显示错误图标，工具提示，显示错误消息字符串。  
  
## <a name="key-properties"></a>键属性  
 <xref:System.Windows.Forms.ErrorProvider>组件的主要属性包括<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>， <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>，和<xref:System.Windows.Forms.ErrorProvider.Icon%2A>。 使用时<xref:System.Windows.Forms.ErrorProvider>组件与数据绑定控件<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>顺序以窗体上显示错误图标组件的情况下，属性必须设置为适当的容器 （通常是 Windows 窗体）。 当在设计器中，将该组件添加<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>属性设置为包含窗体; 如果你在代码中添加控件，必须将它自己。  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>属性可以设置为一个自定义错误图标而不是默认值。 当<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>设置属性，<xref:System.Windows.Forms.ErrorProvider>组件可以显示为数据集的错误消息。 关键方法<xref:System.Windows.Forms.ErrorProvider>组件是<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法，它指定的错误消息字符串，并应显示错误图标的位置。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider>组件不提供辅助功能客户端的内置支持。 若要使用此组件时，使你的应用程序可访问，必须提供其他可访问的反馈机制。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ErrorProvider>  
 [如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
