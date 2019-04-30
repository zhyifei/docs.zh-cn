---
title: Windows 窗体 DataGridView 控件中的性能优化
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 79f74db4ebd095156207a6218f59c0e9ae423085
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012641"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4edbf-102">Windows 窗体 DataGridView 控件中的性能优化</span><span class="sxs-lookup"><span data-stu-id="4edbf-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4edbf-103">当使用大量的数据，`DataGridView`控件可以消耗大量的内存开销，除非谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="4edbf-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="4edbf-104">在内存有限的客户端，可以避免此开销的一些通过避免具有高内存成本的功能。</span><span class="sxs-lookup"><span data-stu-id="4edbf-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="4edbf-105">你还可以管理部分或全部数据维护和检索任务自己使用的虚拟模式以自定义你的方案的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="4edbf-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4edbf-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="4edbf-106">In This Section</span></span>  
 [<span data-ttu-id="4edbf-107">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4edbf-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4edbf-108">介绍如何使用`DataGridView`中来避免不必要的内存使用情况和性能损失，处理大量数据时的控件。</span><span class="sxs-lookup"><span data-stu-id="4edbf-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="4edbf-109">Windows 窗体 DataGridView 控件中的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="4edbf-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4edbf-110">介绍如何使用虚拟模式下以补充或替代标准的数据绑定机制。</span><span class="sxs-lookup"><span data-stu-id="4edbf-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="4edbf-111">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="4edbf-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="4edbf-112">介绍如何实现虚拟模式下的多个事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="4edbf-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="4edbf-113">此外演示了如何实现行级回滚和提交用户编辑。</span><span class="sxs-lookup"><span data-stu-id="4edbf-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="4edbf-114">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="4edbf-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="4edbf-115">介绍如何加载数据按需、 具有更多可显示与可用的客户端内存可以存储数据时非常有用。</span><span class="sxs-lookup"><span data-stu-id="4edbf-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4edbf-116">参考</span><span class="sxs-lookup"><span data-stu-id="4edbf-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4edbf-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="4edbf-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="4edbf-118">为提供参考文档<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4edbf-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edbf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4edbf-119">See also</span></span>

- [<span data-ttu-id="4edbf-120">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="4edbf-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="4edbf-121">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="4edbf-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
