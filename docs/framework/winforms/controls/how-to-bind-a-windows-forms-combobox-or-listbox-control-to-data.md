---
title: "如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据"
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
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b671910ac77b7456492cab871ace3abb61ac7fd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="717d6-102">如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="717d6-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="717d6-103">你可以将绑定<xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ListBox>到数据以执行任务，例如浏览数据库中的数据，输入新数据，或编辑现有数据。</span><span class="sxs-lookup"><span data-stu-id="717d6-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="717d6-104">将 ComboBox 或 ListBox 控件</span><span class="sxs-lookup"><span data-stu-id="717d6-104">To bind a ComboBox or ListBox control</span></span>  
  
1.  <span data-ttu-id="717d6-105">设置`DataSource`绑定到数据源对象的属性。</span><span class="sxs-lookup"><span data-stu-id="717d6-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="717d6-106">可能的数据源包括<xref:System.Windows.Forms.BindingSource>绑定到数据、 数据表、 数据视图、 数据集，数据查看管理器、 数组、 或的任何类都实现<xref:System.Collections.IList>接口。</span><span class="sxs-lookup"><span data-stu-id="717d6-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="717d6-107">有关详细信息，请参阅[支持 Windows 窗体的数据源](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="717d6-107">For more information, see [Data Sources Supported by Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="717d6-108">如果你正在绑定到表，请设置`DisplayMember`为数据源中的列的名称的属性。</span><span class="sxs-lookup"><span data-stu-id="717d6-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="717d6-109">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="717d6-109">\- or -</span></span>  
  
     <span data-ttu-id="717d6-110">如果你正在绑定到<xref:System.Collections.IList>，将显示成员设置为列表中的类型的公共属性。</span><span class="sxs-lookup"><span data-stu-id="717d6-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="717d6-111">如果绑定到数据源不实现<xref:System.ComponentModel.IBindingList>接口，如<xref:System.Collections.ArrayList>，更新数据源时，将不会更新绑定的控件的数据。</span><span class="sxs-lookup"><span data-stu-id="717d6-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="717d6-112">例如，如果你有一个组合框绑定到<xref:System.Collections.ArrayList>和数据添加到<xref:System.Collections.ArrayList>，这些新项将不会出现在组合框中。</span><span class="sxs-lookup"><span data-stu-id="717d6-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="717d6-113">不过，你可以强制组合框，以通过调用更新<xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>和<xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>的实例上的方法<xref:System.Windows.Forms.BindingContext>控件所绑定到类。</span><span class="sxs-lookup"><span data-stu-id="717d6-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717d6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="717d6-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="717d6-115">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="717d6-115">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="717d6-116">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="717d6-116">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="717d6-117">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="717d6-117">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
