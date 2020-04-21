---
title: 如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 2fe4458aa43144a9c29ed67fd7bee99a37fe1434
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739681"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知
当<xref:System.Windows.Forms.BindingSource>数据源中包含的类型实现<xref:System.ComponentModel.INotifyPropertyChanged>时，组件会自动检测数据源中的更改，并在更改属性值时引发<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>事件。 此更改检测很有用，因为绑定到 的<xref:System.Windows.Forms.BindingSource>控件会随着数据源值的变化而自动更新。  
  
> [!NOTE]
> 如果数据源实现 <xref:System.ComponentModel.INotifyPropertyChanged>，并且你正在执行异步操作，则不应更改后台线程上的数据源。 相反，应读取后台线程上的数据，并将数据合并到 UI 线程上的列表。  
  
## <a name="example"></a>示例  
 下面的代码示例演示了如何简单实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口。 它还演示了当将 <xref:System.Windows.Forms.BindingSource> 绑定到 <xref:System.ComponentModel.INotifyPropertyChanged> 类型的列表时，<xref:System.Windows.Forms.BindingSource> 如何将数据源更改自动传递到绑定控件。  
  
 如果使用 `CallerMemberName` 特性，则调用 `NotifyPropertyChanged` 方法不必将属性名称指定为字符串参数。 有关详细信息，请参阅[呼叫者信息 （C#）](../../../csharp/language-reference/attributes/caller-information.md)或[呼叫者信息（可视基本）。](../../../visual-basic/programming-guide/concepts/caller-information.md)  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对系统、系统、数据、系统、绘图和系统.Windows.窗体程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [BindingSource 组件](bindingsource-component.md)
- [如何：使用 BindingSource ResetItem 方法引发更改通知](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
