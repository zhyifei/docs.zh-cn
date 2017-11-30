---
title: "如何：实现 INotifyPropertyChanged 接口"
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
helpviewer_keywords: INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 54dc436ec40f001ab1bf90acaedf22745d35d1b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="3211a-102">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="3211a-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="3211a-103">下面的代码示例演示如何实现<xref:System.ComponentModel.INotifyPropertyChanged>接口。</span><span class="sxs-lookup"><span data-stu-id="3211a-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="3211a-104">在 Windows 窗体数据绑定中使用的业务对象上实现此接口。</span><span class="sxs-lookup"><span data-stu-id="3211a-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="3211a-105">在实现时，该接口绑定控件中通信在业务对象上的属性更改。</span><span class="sxs-lookup"><span data-stu-id="3211a-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3211a-106">示例</span><span class="sxs-lookup"><span data-stu-id="3211a-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3211a-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3211a-107">See Also</span></span>  
 [<span data-ttu-id="3211a-108">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="3211a-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [<span data-ttu-id="3211a-109">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="3211a-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="3211a-110">如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知</span><span class="sxs-lookup"><span data-stu-id="3211a-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [<span data-ttu-id="3211a-111">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="3211a-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
