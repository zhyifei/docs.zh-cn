---
title: Windows 窗体数据绑定中的更改通知
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 79ad52b6db8cb7be7f4e3162b8f726e8cbe22dcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Windows 窗体数据绑定中的更改通知
Windows 窗体数据绑定的最重要概念之一是*更改通知*。 若要确保你的数据源和绑定的控件始终具有最新的数据，必须添加数据绑定的更改通知。 具体而言，你想要确保对其数据源，所做的更改，会通知绑定的控件，并且数据源会通知的控件的绑定属性所做的更改。  
  
 有不同种类的更改通知，具体取决于数据绑定的类型：  
  
-   简单绑定，在其中的单个控件属性绑定到对象的单个实例。  
  
-   基于列表的绑定，可以包括单个控件属性绑定到列表中的项的属性或控件属性绑定到的对象的列表。  
  
 此外，如果要创建想要用于数据绑定的 Windows 窗体控件，则必须应用*PropertyName*于这些控件，更改模式，以便对控件的绑定属性的更改传播到数据源。  
  
## <a name="change-notification-for-simple-binding"></a>简单绑定的更改通知  
 对于简单绑定，业务对象绑定属性的值更改时必须提供更改通知。 你可以执行此操作通过公开*PropertyName*Changed 事件的业务对象并将业务对象绑定到控件与每个属性<xref:System.Windows.Forms.BindingSource>或在其中实现业务对象的首选的方法<xref:System.ComponentModel.INotifyPropertyChanged>接口并引发<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>事件的属性的值更改时。 有关详细信息，请参阅[如何： 实现 INotifyPropertyChanged 接口](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)。 当你使用实现的对象<xref:System.ComponentModel.INotifyPropertyChanged>接口，则不需要使用<xref:System.Windows.Forms.BindingSource>将对象绑定到控件，但使用<xref:System.Windows.Forms.BindingSource>建议。  
  
## <a name="change-notification-for-list-based-binding"></a>基于列表的绑定的更改通知  
 Windows 窗体取决于绑定的列表，以提供 （列表项属性值更改） 的属性更改和更改的列表 （删除项或添加到列表） 绑定控件的信息。 因此，必须实现用于数据绑定列表<xref:System.ComponentModel.IBindingList>，该属性提供两种类型的更改通知。 <xref:System.ComponentModel.BindingList%601>是的一般实现<xref:System.ComponentModel.IBindingList>，专用于 Windows 窗体数据绑定。 你可以创建<xref:System.ComponentModel.BindingList%601>，其中包含实现的业务对象类型<xref:System.ComponentModel.INotifyPropertyChanged>和列表将自动转换<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>事件<xref:System.ComponentModel.IBindingList.ListChanged>事件。 如果绑定的列表不是<xref:System.ComponentModel.IBindingList>，你必须通过绑定到 Windows 窗体控件的对象的列表<xref:System.Windows.Forms.BindingSource>组件。 <xref:System.Windows.Forms.BindingSource>组件将提供类似于其中的属性列表转换<xref:System.ComponentModel.BindingList%601>。 有关详细信息，请参阅[如何： 使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)。  
  
## <a name="change-notification-for-custom-controls"></a>自定义控件的更改通知  
 最后，从控件端必须公开*PropertyName*旨在绑定到数据的每个属性的 Changed 事件。 然后，对控件属性的更改会传播到绑定的数据源。 有关详细信息，请参阅[如何： 应用 PropertyNameChanged 模式](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Windows 窗体支持的数据源](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [数据绑定和 Windows 窗体](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
