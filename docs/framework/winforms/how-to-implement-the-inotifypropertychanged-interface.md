---
title: 如何：实现 INotifyPropertyChanged 接口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: c92406899cffa56a1001f50f89cb53303df5da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560069"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="05d5b-102">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="05d5b-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="05d5b-103">下面的代码示例演示如何实现<xref:System.ComponentModel.INotifyPropertyChanged>接口。</span><span class="sxs-lookup"><span data-stu-id="05d5b-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="05d5b-104">在 Windows 窗体数据绑定中使用的业务对象上实现此接口。</span><span class="sxs-lookup"><span data-stu-id="05d5b-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="05d5b-105">实现时，该接口与绑定控件通信业务对象的属性更改。</span><span class="sxs-lookup"><span data-stu-id="05d5b-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05d5b-106">示例</span><span class="sxs-lookup"><span data-stu-id="05d5b-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="05d5b-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="05d5b-107">See also</span></span>
- [<span data-ttu-id="05d5b-108">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="05d5b-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="05d5b-109">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="05d5b-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="05d5b-110">如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知</span><span class="sxs-lookup"><span data-stu-id="05d5b-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="05d5b-111">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="05d5b-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
