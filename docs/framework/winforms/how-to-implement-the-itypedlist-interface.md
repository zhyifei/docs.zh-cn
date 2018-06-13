---
title: 如何：实现 ITypedList 接口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 181879d3e41e0dd140c79a4c63d52e6999acf86d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538058"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="29fca-102">如何：实现 ITypedList 接口</span><span class="sxs-lookup"><span data-stu-id="29fca-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="29fca-103">实现<xref:System.ComponentModel.ITypedList>界面，以启用可绑定列表的架构发现。</span><span class="sxs-lookup"><span data-stu-id="29fca-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29fca-104">示例</span><span class="sxs-lookup"><span data-stu-id="29fca-104">Example</span></span>  
 <span data-ttu-id="29fca-105">下面的代码示例演示如何实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="29fca-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="29fca-106">名为的泛型类型`SortableBindingList`派生自<xref:System.ComponentModel.BindingList%601>类并实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="29fca-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="29fca-107">简单的类名为`Customer`提供数据，绑定到的标头<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="29fca-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29fca-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="29fca-108">Compiling the Code</span></span>  
 <span data-ttu-id="29fca-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="29fca-109">This example requires:</span></span>  
  
-   <span data-ttu-id="29fca-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="29fca-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29fca-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="29fca-111">See Also</span></span>  
 <xref:System.ComponentModel.ITypedList>  
 <xref:System.ComponentModel.BindingList%601>  
 <xref:System.ComponentModel.IBindingList>  
 [<span data-ttu-id="29fca-112">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="29fca-112">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
