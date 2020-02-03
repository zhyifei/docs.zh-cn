---
title: 将 ComboBox 或 ListBox 控件绑定到数据
ms.date: 03/30/2017
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742030"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="37656-102">如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="37656-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="37656-103">您可以将 <xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ListBox> 绑定到数据，以执行诸如浏览数据库中的数据、输入新数据或编辑现有数据等任务。</span><span class="sxs-lookup"><span data-stu-id="37656-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="37656-104">绑定 ComboBox 或 ListBox 控件</span><span class="sxs-lookup"><span data-stu-id="37656-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="37656-105">将 `DataSource` 属性设置为数据源对象。</span><span class="sxs-lookup"><span data-stu-id="37656-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="37656-106">可能的数据源包括绑定到数据、数据表、数据视图、数据集、数据视图管理器、数组或实现 <xref:System.Collections.IList> 接口的任何类的 <xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="37656-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="37656-107">有关详细信息，请参阅[Windows 窗体支持的数据源](../data-sources-supported-by-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="37656-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="37656-108">如果要绑定到表，请将 `DisplayMember` 属性设置为数据源中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="37656-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="37656-109">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="37656-109">\- or -</span></span>  
  
     <span data-ttu-id="37656-110">如果要绑定到 <xref:System.Collections.IList>，请在列表中将显示成员设置为该类型的公共属性。</span><span class="sxs-lookup"><span data-stu-id="37656-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="37656-111">如果绑定到不实现 <xref:System.ComponentModel.IBindingList> 接口的数据源（如 <xref:System.Collections.ArrayList>），则在更新数据源时，将不会更新绑定控件的数据。</span><span class="sxs-lookup"><span data-stu-id="37656-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="37656-112">例如，如果将组合框绑定到 <xref:System.Collections.ArrayList> 并将数据添加到 <xref:System.Collections.ArrayList>中，则这些新项将不会出现在组合框中。</span><span class="sxs-lookup"><span data-stu-id="37656-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="37656-113">但是，你可以通过调用 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>，并 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 方法在控件所绑定到的 <xref:System.Windows.Forms.BindingContext> 类的实例上，来强制更新组合框。</span><span class="sxs-lookup"><span data-stu-id="37656-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37656-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37656-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="37656-115">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="37656-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="37656-116">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="37656-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="37656-117">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="37656-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
