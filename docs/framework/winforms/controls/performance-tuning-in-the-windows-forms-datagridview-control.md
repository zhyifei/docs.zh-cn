---
title: "Windows 窗体 DataGridView 控件中的性能优化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的性能优化
在使用大量的数据，`DataGridView`控件可以使用大量的内存开销，除非谨慎使用。 上内存有限的客户端，你可以避免此开销的一些通过避免功能，具有高内存成本。 你还可以管理的部分或全部数据维护和检索任务自己使用的虚拟模式以便自定义你的方案的内存使用量。  
  
## <a name="in-this-section"></a>本节内容  
 [有关缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 介绍如何使用`DataGridView`控件的方式来处理大量数据时避免不必要的内存使用情况和性能损失。  
  
 [Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 介绍如何使用虚拟模式来补充或取代的标准的数据绑定机制。  
  
 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 描述如何实现多个虚拟模式事件的处理程序。 此外演示如何实现行级回滚和提交用户编辑。  
  
 [在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 介绍如何加载点播情况下，这很有用，如果你具有要显示与可用的客户端内存可以存储的详细数据的数据。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 提供的参考文档<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性。  
  
## <a name="see-also"></a>请参阅  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
