---
title: "TableLayoutPanel 控件中的自动调整大小行为"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="438ef-102">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="438ef-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="438ef-103">非重复 AutoSize 行为</span><span class="sxs-lookup"><span data-stu-id="438ef-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="438ef-104"><xref:System.Windows.Forms.TableLayoutPanel>控件支持自动调整大小行为通过以下方式：</span><span class="sxs-lookup"><span data-stu-id="438ef-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
-   <span data-ttu-id="438ef-105">通过<xref:System.Windows.Forms.Control.AutoSize%2A>属性;</span><span class="sxs-lookup"><span data-stu-id="438ef-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
-   <span data-ttu-id="438ef-106">通过<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性<xref:System.Windows.Forms.TableLayoutPanel>控件的列和行样式。</span><span class="sxs-lookup"><span data-stu-id="438ef-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="438ef-107">具有行和列样式的 AutoSize 属性</span><span class="sxs-lookup"><span data-stu-id="438ef-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="438ef-108">下表描述了之间的交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性和<xref:System.Windows.Forms.TableLayoutPanel>控件的列和行样式。</span><span class="sxs-lookup"><span data-stu-id="438ef-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="438ef-109">AutoSize 设置</span><span class="sxs-lookup"><span data-stu-id="438ef-109">AutoSize setting</span></span>|<span data-ttu-id="438ef-110">样式交互</span><span class="sxs-lookup"><span data-stu-id="438ef-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="438ef-111"><xref:System.Windows.Forms.TableLayoutPanel>控件将继续从左到右，并为列或行或按以下顺序分配空间。</span><span class="sxs-lookup"><span data-stu-id="438ef-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="438ef-112">1.如果<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性设置为<xref:System.Windows.Forms.SizeType.Absolute>，由指定的像素数<xref:System.Windows.Forms.ColumnStyle.Width%2A>或<xref:System.Windows.Forms.RowStyle.Height%2A>分配。</span><span class="sxs-lookup"><span data-stu-id="438ef-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="438ef-113">2.如果<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>属性设置为<xref:System.Windows.Forms.SizeType.AutoSize>，返回的子控件的像素数<xref:System.Windows.Forms.Control.GetPreferredSize%2A>分配方法。</span><span class="sxs-lookup"><span data-stu-id="438ef-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="438ef-114">3.所有的空格后面<xref:System.Windows.Forms.SizeType.Absolute>和<xref:System.Windows.Forms.SizeType.AutoSize>列或行已分配，任何列或行与<xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>设置为<xref:System.Windows.Forms.SizeType.Percent>用于按比例分配的剩余可用空间</span><span class="sxs-lookup"><span data-stu-id="438ef-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="438ef-115">类似于前面的交互，出现异常，<xref:System.Windows.Forms.SizeType.Percent>列或行获取自动调整大小方面。</span><span class="sxs-lookup"><span data-stu-id="438ef-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="438ef-116"><xref:System.Windows.Forms.TableLayoutPanel>控件扩展的列或行以创建足够的可用空间，以便任何列或行<xref:System.Windows.Forms.SizeType.Percent>样式剪裁掉其内容。</span><span class="sxs-lookup"><span data-stu-id="438ef-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="438ef-117"><xref:System.Windows.Forms.TableLayoutPanel>控件分配根据到按比例的新空间<xref:System.Windows.Forms.ColumnStyle.Width%2A>或<xref:System.Windows.Forms.RowStyle.Height%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="438ef-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="438ef-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="438ef-118">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="438ef-119">TableLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="438ef-119">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
