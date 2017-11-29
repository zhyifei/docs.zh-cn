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
ms.openlocfilehash: 452c55d38a896ec96e0992a4b9826f08dc4caa0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="dd85e-102">Windows 窗体 DataGridView 控件中的性能优化</span><span class="sxs-lookup"><span data-stu-id="dd85e-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dd85e-103">在使用大量的数据，`DataGridView`控件可以使用大量的内存开销，除非谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="dd85e-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="dd85e-104">上内存有限的客户端，你可以避免此开销的一些通过避免功能，具有高内存成本。</span><span class="sxs-lookup"><span data-stu-id="dd85e-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="dd85e-105">你还可以管理的部分或全部数据维护和检索任务自己使用的虚拟模式以便自定义你的方案的内存使用量。</span><span class="sxs-lookup"><span data-stu-id="dd85e-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd85e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="dd85e-106">In This Section</span></span>  
 [<span data-ttu-id="dd85e-107">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="dd85e-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd85e-108">介绍如何使用`DataGridView`控件的方式来处理大量数据时避免不必要的内存使用情况和性能损失。</span><span class="sxs-lookup"><span data-stu-id="dd85e-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="dd85e-109">Windows 窗体 DataGridView 控件中的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="dd85e-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd85e-110">介绍如何使用虚拟模式来补充或取代的标准的数据绑定机制。</span><span class="sxs-lookup"><span data-stu-id="dd85e-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="dd85e-111">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="dd85e-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="dd85e-112">描述如何实现多个虚拟模式事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="dd85e-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="dd85e-113">此外演示如何实现行级回滚和提交用户编辑。</span><span class="sxs-lookup"><span data-stu-id="dd85e-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="dd85e-114">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="dd85e-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="dd85e-115">介绍如何加载点播情况下，这很有用，如果你具有要显示与可用的客户端内存可以存储的详细数据的数据。</span><span class="sxs-lookup"><span data-stu-id="dd85e-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dd85e-116">参考</span><span class="sxs-lookup"><span data-stu-id="dd85e-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="dd85e-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="dd85e-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="dd85e-118">提供的参考文档<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dd85e-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd85e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd85e-119">See Also</span></span>  
 [<span data-ttu-id="dd85e-120">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="dd85e-120">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="dd85e-121">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="dd85e-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
