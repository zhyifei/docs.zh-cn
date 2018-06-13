---
title: 如何：实现 INotifyPropertyChanged 接口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 8f64b51a7d56f609399baac613a651e82b91e6df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536407"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>如何：实现 INotifyPropertyChanged 接口
下面的代码示例演示如何实现<xref:System.ComponentModel.INotifyPropertyChanged>接口。 在 Windows 窗体数据绑定中使用的业务对象上实现此接口。 在实现时，该接口绑定控件中通信在业务对象上的属性更改。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [如何：应用 PropertyNameChanged 模式](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [Windows 窗体数据绑定中的更改通知](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
