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
ms.openlocfilehash: 2463a9c77a9836ff251e799056cc5131bf6c99e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084904"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="b3d13-102">如何：实现 ITypedList 接口</span><span class="sxs-lookup"><span data-stu-id="b3d13-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="b3d13-103">实现<xref:System.ComponentModel.ITypedList>接口实现的可绑定列表的架构。</span><span class="sxs-lookup"><span data-stu-id="b3d13-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3d13-104">示例</span><span class="sxs-lookup"><span data-stu-id="b3d13-104">Example</span></span>  
 <span data-ttu-id="b3d13-105">下面的代码示例演示如何实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="b3d13-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="b3d13-106">名为的泛型类型`SortableBindingList`派生自<xref:System.ComponentModel.BindingList%601>类，并实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="b3d13-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="b3d13-107">一个简单的类名为`Customer`提供了数据绑定到的标头<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="b3d13-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3d13-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="b3d13-108">Compiling the Code</span></span>  
 <span data-ttu-id="b3d13-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b3d13-109">This example requires:</span></span>  
  
-   <span data-ttu-id="b3d13-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b3d13-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d13-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3d13-111">See also</span></span>

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="b3d13-112">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b3d13-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
