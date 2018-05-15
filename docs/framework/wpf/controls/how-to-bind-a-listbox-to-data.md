---
title: 如何：将 ListBox 绑定到数据
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 186d25750c5ce196a5e46c02f0f56e2440ea3a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="db456-102">如何：将 ListBox 绑定到数据</span><span class="sxs-lookup"><span data-stu-id="db456-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="db456-103">应用程序开发人员可以创建<xref:System.Windows.Controls.ListBox>而无需指定每个内容控件<xref:System.Windows.Controls.ListBoxItem>单独。</span><span class="sxs-lookup"><span data-stu-id="db456-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="db456-104">你可以使用数据绑定来将数据绑定到的各个项。</span><span class="sxs-lookup"><span data-stu-id="db456-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="db456-105">下面的示例演示如何创建<xref:System.Windows.Controls.ListBox>来填充<xref:System.Windows.Controls.ListBoxItem>元素通过数据绑定到数据源调用*颜色*。</span><span class="sxs-lookup"><span data-stu-id="db456-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="db456-106">在这种情况下不需要使用<xref:System.Windows.Controls.ListBoxItem>标记来指定每个项的内容。</span><span class="sxs-lookup"><span data-stu-id="db456-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db456-107">示例</span><span class="sxs-lookup"><span data-stu-id="db456-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="db456-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="db456-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="db456-109">控件</span><span class="sxs-lookup"><span data-stu-id="db456-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
