---
title: 如何：将 ListBox 绑定到数据
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106427"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="7b38a-102">如何：将 ListBox 绑定到数据</span><span class="sxs-lookup"><span data-stu-id="7b38a-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="7b38a-103">应用程序开发人员可以创建<xref:System.Windows.Controls.ListBox>而无需指定的每个内容控件<xref:System.Windows.Controls.ListBoxItem>单独。</span><span class="sxs-lookup"><span data-stu-id="7b38a-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="7b38a-104">数据绑定可用于将数据绑定到的各个项。</span><span class="sxs-lookup"><span data-stu-id="7b38a-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="7b38a-105">下面的示例演示如何创建<xref:System.Windows.Controls.ListBox>填充<xref:System.Windows.Controls.ListBoxItem>通过数据绑定到的数据源的元素*颜色*。</span><span class="sxs-lookup"><span data-stu-id="7b38a-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="7b38a-106">在这种情况下不需要使用<xref:System.Windows.Controls.ListBoxItem>标记，以指定每个项的内容。</span><span class="sxs-lookup"><span data-stu-id="7b38a-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b38a-107">示例</span><span class="sxs-lookup"><span data-stu-id="7b38a-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7b38a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b38a-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="7b38a-109">控件</span><span class="sxs-lookup"><span data-stu-id="7b38a-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
