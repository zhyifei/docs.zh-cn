---
title: 从 DomainUpDown 控件中删除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735765"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="bc7de-102">如何：从 Windows 窗体 DomainUpDown 控件移除项</span><span class="sxs-lookup"><span data-stu-id="bc7de-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="bc7de-103">可以通过调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 类的 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 或 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法，从 Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件中删除项。</span><span class="sxs-lookup"><span data-stu-id="bc7de-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="bc7de-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 方法删除特定项，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法按项的位置删除该项。</span><span class="sxs-lookup"><span data-stu-id="bc7de-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="bc7de-105">删除项</span><span class="sxs-lookup"><span data-stu-id="bc7de-105">To remove an item</span></span>  
  
- <span data-ttu-id="bc7de-106">使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 类的 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 方法，按名称删除项。</span><span class="sxs-lookup"><span data-stu-id="bc7de-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="bc7de-107">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="bc7de-107">-or-</span></span>  
  
- <span data-ttu-id="bc7de-108">使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法按项的位置删除项。</span><span class="sxs-lookup"><span data-stu-id="bc7de-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc7de-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc7de-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bc7de-110">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="bc7de-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="bc7de-111">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="bc7de-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
