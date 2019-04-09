---
title: 如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 32f58dc8b8b96a3d8660550d8ce7696839587ddc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080665"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="ae1f4-102">如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项</span><span class="sxs-lookup"><span data-stu-id="ae1f4-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="ae1f4-103">可以将项添加到 Windows 窗体<xref:System.Windows.Forms.DomainUpDown>在代码中的控件。</span><span class="sxs-lookup"><span data-stu-id="ae1f4-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="ae1f4-104">调用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>或<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>方法<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类将项添加到控件的<xref:System.Windows.Forms.DomainUpDown.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ae1f4-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="ae1f4-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>方法将项添加到集合的末尾时<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>方法的指定位置中添加项。</span><span class="sxs-lookup"><span data-stu-id="ae1f4-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="ae1f4-106">若要添加新项</span><span class="sxs-lookup"><span data-stu-id="ae1f4-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="ae1f4-107">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>方法将项添加到的项列表的末尾。</span><span class="sxs-lookup"><span data-stu-id="ae1f4-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="ae1f4-108">或</span><span class="sxs-lookup"><span data-stu-id="ae1f4-108">-or-</span></span>  
  
2.  <span data-ttu-id="ae1f4-109">使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>方法向列表中的指定位置插入项。</span><span class="sxs-lookup"><span data-stu-id="ae1f4-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ae1f4-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae1f4-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ae1f4-111">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="ae1f4-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="ae1f4-112">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="ae1f4-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
