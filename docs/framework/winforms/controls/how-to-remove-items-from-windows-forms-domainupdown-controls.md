---
title: 如何：从 Windows 窗体 DomainUpDown 控件移除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 0c07365f5be2e419b4049a466949fed2d884d897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913128"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="661bd-102">如何：从 Windows 窗体 DomainUpDown 控件移除项</span><span class="sxs-lookup"><span data-stu-id="661bd-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="661bd-103">可以从 Windows 窗体中移除项<xref:System.Windows.Forms.DomainUpDown>控件通过调用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>或<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法的<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类。</span><span class="sxs-lookup"><span data-stu-id="661bd-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="661bd-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法中删除特定项，而<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法中移除的项按其位置。</span><span class="sxs-lookup"><span data-stu-id="661bd-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="661bd-105">若要删除项</span><span class="sxs-lookup"><span data-stu-id="661bd-105">To remove an item</span></span>  
  
- <span data-ttu-id="661bd-106">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法的<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类名称中删除项。</span><span class="sxs-lookup"><span data-stu-id="661bd-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="661bd-107">或</span><span class="sxs-lookup"><span data-stu-id="661bd-107">-or-</span></span>  
  
- <span data-ttu-id="661bd-108">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法中删除的项按其位置。</span><span class="sxs-lookup"><span data-stu-id="661bd-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="661bd-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="661bd-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="661bd-110">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="661bd-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="661bd-111">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="661bd-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
