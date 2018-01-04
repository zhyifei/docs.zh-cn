---
title: "如何：从 Windows 窗体 DomainUpDown 控件移除项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17972aa9cb1626793ab04d317bb66d2774899cfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="04360-102">如何：从 Windows 窗体 DomainUpDown 控件移除项</span><span class="sxs-lookup"><span data-stu-id="04360-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="04360-103">你可以从 Windows 窗体中移除项<xref:System.Windows.Forms.DomainUpDown>通过调用控件<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>或<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类。</span><span class="sxs-lookup"><span data-stu-id="04360-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="04360-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法中删除特定项，而<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法中移除一个项按其位置。</span><span class="sxs-lookup"><span data-stu-id="04360-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="04360-105">若要移除一个项</span><span class="sxs-lookup"><span data-stu-id="04360-105">To remove an item</span></span>  
  
-   <span data-ttu-id="04360-106">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类可按名称移除一个项。</span><span class="sxs-lookup"><span data-stu-id="04360-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="04360-107">或</span><span class="sxs-lookup"><span data-stu-id="04360-107">-or-</span></span>  
  
-   <span data-ttu-id="04360-108">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法来删除按其位置的项。</span><span class="sxs-lookup"><span data-stu-id="04360-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="04360-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="04360-109">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="04360-110">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="04360-110">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="04360-111">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="04360-111">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
