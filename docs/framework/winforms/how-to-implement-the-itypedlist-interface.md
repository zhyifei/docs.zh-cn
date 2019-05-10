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
ms.openlocfilehash: 3f5a5032166087c7398d310071b3998c845e2780
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630742"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="73a7f-102">如何：实现 ITypedList 接口</span><span class="sxs-lookup"><span data-stu-id="73a7f-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="73a7f-103">实现<xref:System.ComponentModel.ITypedList>接口实现的可绑定列表的架构。</span><span class="sxs-lookup"><span data-stu-id="73a7f-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73a7f-104">示例</span><span class="sxs-lookup"><span data-stu-id="73a7f-104">Example</span></span>  
 <span data-ttu-id="73a7f-105">下面的代码示例演示如何实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="73a7f-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="73a7f-106">名为的泛型类型`SortableBindingList`派生自<xref:System.ComponentModel.BindingList%601>类，并实现<xref:System.ComponentModel.ITypedList>接口。</span><span class="sxs-lookup"><span data-stu-id="73a7f-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="73a7f-107">一个简单的类名为`Customer`提供了数据绑定到的标头<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="73a7f-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73a7f-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="73a7f-108">Compiling the Code</span></span>  
 <span data-ttu-id="73a7f-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="73a7f-109">This example requires:</span></span>  
  
- <span data-ttu-id="73a7f-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="73a7f-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a7f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="73a7f-111">See also</span></span>

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="73a7f-112">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="73a7f-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
