---
title: 如何：实现 INotifyPropertyChanged 接口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 51c0b1fa535921b7b33a16f55bdc8b76d6125e72
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704084"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="63dc4-102">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="63dc4-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="63dc4-103">下面的代码示例演示如何实现<xref:System.ComponentModel.INotifyPropertyChanged>接口。</span><span class="sxs-lookup"><span data-stu-id="63dc4-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="63dc4-104">在 Windows 窗体数据绑定中使用的业务对象上实现此接口。</span><span class="sxs-lookup"><span data-stu-id="63dc4-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="63dc4-105">实现时，该接口与绑定控件通信业务对象的属性更改。</span><span class="sxs-lookup"><span data-stu-id="63dc4-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63dc4-106">示例</span><span class="sxs-lookup"><span data-stu-id="63dc4-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="63dc4-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="63dc4-107">See also</span></span>
- [<span data-ttu-id="63dc4-108">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="63dc4-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="63dc4-109">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="63dc4-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="63dc4-110">如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知</span><span class="sxs-lookup"><span data-stu-id="63dc4-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="63dc4-111">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="63dc4-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
