---
title: 与数据绑定相关的接口
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 4e40f7ec1922cdf43e6a0b8f5734acaaeefbc514
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834592"
---
# <a name="interfaces-related-to-data-binding"></a>与数据绑定相关的接口

使用 ADO.NET，可以创建许多不同的数据结构，以满足应用程序的绑定需求和正在处理的数据的需要。 你可能希望创建自己的类，以便在 Windows 窗体中提供或使用数据。 这些对象可以提供各种级别的功能和复杂性，从基本的数据绑定，到提供设计时支持、错误检查、更改通知，甚至是支持对数据本身所做更改的结构化回退。

## <a name="consumers-of-data-binding-interfaces"></a>数据绑定接口的使用者

以下各节描述了两组接口对象。 第一组列出数据源作者在数据源上实现的接口。 这些接口旨在由数据源使用者使用，在多数情况下，这些使用者是 Windows 窗体控件或组件。 第二组列出面向组件作者设计的接口。 组件作者在创建支持数据绑定的组件时使用这些接口，以便它们能够被 Windows 窗体数据绑定引擎使用。 可以在与窗体关联的类中实现这些接口以启用数据绑定；每种情况都表示一个类，该类所实现的接口支持与数据进行交互。 Visual Studio 快速应用程序开发（RAD）数据设计体验工具已充分利用此功能。

### <a name="interfaces-for-implementation-by-data-source-authors"></a>要由数据源作者实现的接口

下列接口设计为由 Windows 窗体控件使用：

- <xref:System.Collections.IList>交互

  实现<xref:System.Collections.IList>接口的类可以<xref:System.Array>是、 <xref:System.Collections.ArrayList>或<xref:System.Collections.CollectionBase>。 它们是类型<xref:System.Object>的项的索引列表。 这些列表必须包含同源类型，因为索引中的第一项确定类型。 <xref:System.Collections.IList>仅在运行时可用于绑定。

  > [!NOTE]
  > 如果要创建与 Windows 窗体绑定的业务对象列表，则应考虑使用<xref:System.ComponentModel.BindingList%601>。 <xref:System.ComponentModel.BindingList%601>是一个可扩展类，该类实现双向 Windows 窗体数据绑定所需的主要接口。

- <xref:System.ComponentModel.IBindingList>交互

  实现<xref:System.ComponentModel.IBindingList>接口的类提供更高级别的数据绑定功能。 此实现在列表项更改时（例如，客户列表中的第三项更改了 Address 字段）和列表本身更改时（例如，列表中项的数量增加或减少）都提供基本的排序功能和更改通知。 如果计划将多个控件绑定到同一个数据，但是希望将在其中某个控件中进行的数据更改传播到其他绑定控件，更改通知就非常重要。

  > [!NOTE]
  > 通过属性为<xref:System.ComponentModel.IBindingList>接口启用更改通知<xref:System.ComponentModel.IBindingList.ListChanged> ，引发事件时`true`，指示列表已更改或列表中的项发生更改。 <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A>

  更改类型由<xref:System.ComponentModel.ListChangedType> <xref:System.ComponentModel.ListChangedEventArgs>参数的属性描述。 因此，当数据模型进行更新时，任何依赖视图（例如，绑定到同一个数据源的其他控件）也会进行更新。 但是，列表中包含的对象必须在其更改时通知列表，这样列表才能引发<xref:System.ComponentModel.IBindingList.ListChanged>事件。

  > [!NOTE]
  > <xref:System.ComponentModel.BindingList%601>提供<xref:System.ComponentModel.IBindingList>接口的泛型实现。

- <xref:System.ComponentModel.IBindingListView>交互

  实现<xref:System.ComponentModel.IBindingListView>接口的类提供的实现的<xref:System.ComponentModel.IBindingList>所有功能，以及筛选和高级排序功能。 此实现使用属性描述符-方向对提供基于字符串的筛选和多列排序能力。

- <xref:System.ComponentModel.IEditableObject>交互

  实现<xref:System.ComponentModel.IEditableObject>接口的类允许对象控制对该对象的更改是永久性的。 此实现为你提供<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>了<xref:System.ComponentModel.IEditableObject.EndEdit%2A>、和<xref:System.ComponentModel.IEditableObject.CancelEdit%2A>方法，使你能够回滚对对象所做的更改。 下面简要说明了<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>、 <xref:System.ComponentModel.IEditableObject.EndEdit%2A>和<xref:System.ComponentModel.IEditableObject.CancelEdit%2A>方法的功能，并说明了它们彼此之间的作用，以启用对数据所做更改的可能回滚：

  - <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>方法指示对对象的编辑开始。 实现此接口的对象需要在<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>方法调用后存储任何更新，这样一来， <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>如果调用方法，就可以丢弃更新。 在数据绑定 Windows 窗体中，可以在<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>单个编辑事务的作用域内多次调用（ <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>例如<xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A>，、、）。 的<xref:System.ComponentModel.IEditableObject>实现应跟踪是否<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>已调用，并忽略对<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>的后续调用。 由于可以多次调用此方法，因此对它的后续调用非常重要;也就是说，后续<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>调用不会销毁已进行的更新，也无法更改第一次<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>调用时保存的数据。

  - 如果<xref:System.ComponentModel.IEditableObject.EndEdit%2A>对象当前处于编辑模式<xref:System.ComponentModel.IEditableObject.BeginEdit%2A> ，则方法会将调用后的任何更改推送到基础对象。

  - <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>方法会放弃对对象所做的任何更改。

  有关<xref:System.ComponentModel.IEditableObject.BeginEdit%2A>、<xref:System.ComponentModel.IEditableObject.EndEdit%2A> 和 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 方法的工作方式的详细信息，请参阅[将数据保存回数据库](/visualstudio/data-tools/save-data-back-to-the-database)。

  此数据功能的事务性概念由<xref:System.Windows.Forms.DataGridView>控件使用。

- <xref:System.ComponentModel.ICancelAddNew>交互

  实现<xref:System.ComponentModel.ICancelAddNew>接口的类通常<xref:System.ComponentModel.IBindingList>实现接口，并允许您使用<xref:System.ComponentModel.IBindingList.AddNew%2A>方法回滚对数据源所做的添加。 如果数据源实现了<xref:System.ComponentModel.IBindingList>接口，则还应让它<xref:System.ComponentModel.ICancelAddNew>实现接口。

- <xref:System.ComponentModel.IDataErrorInfo>交互

  实现<xref:System.ComponentModel.IDataErrorInfo>接口的类允许对象向绑定控件提供自定义错误信息：

  - @No__t-0 属性返回常规错误消息文本（例如，"发生错误"）。

  - @No__t-0 属性返回一个字符串，其中包含来自该列的特定错误消息（例如，"`State` 列中的值无效"）。

- <xref:System.Collections.IEnumerable>交互

  用于实现<xref:System.Collections.IEnumerable>接口的类通常由 ASP.NET 使用。 仅可通过<xref:System.Windows.Forms.BindingSource>组件获取对此接口的 Windows 窗体支持。

  > [!NOTE]
  > 组件将所有<xref:System.Collections.IEnumerable>项复制到一个单独的列表中，以便进行绑定。 <xref:System.Windows.Forms.BindingSource>

- <xref:System.ComponentModel.ITypedList>交互

  实现<xref:System.ComponentModel.ITypedList>接口的集合类提供控制向绑定控件公开的顺序和属性集的功能。

  > [!NOTE]
  > 实现<xref:System.ComponentModel.ITypedList.GetItemProperties%2A>方法时， <xref:System.ComponentModel.PropertyDescriptor>如果数组不为 null，则数组中的最后一项将是描述列表属性（另一项列表）的属性描述符。

- <xref:System.ComponentModel.ICustomTypeDescriptor>交互

  实现<xref:System.ComponentModel.ICustomTypeDescriptor>接口的类提供有关其自身的动态信息。 此接口类似于， <xref:System.ComponentModel.ITypedList>但用于对象而不是列表。 使用此接口<xref:System.Data.DataRowView>来投影基础行的架构。 的简单实现<xref:System.ComponentModel.ICustomTypeDescriptor> <xref:System.ComponentModel.CustomTypeDescriptor>由类提供。

  > [!NOTE]
  > 若要支持对实现<xref:System.ComponentModel.ICustomTypeDescriptor>的类型的设计时绑定，该类型还必须实现<xref:System.ComponentModel.IComponent> ，并作为窗体上的实例存在。

- <xref:System.ComponentModel.IListSource>交互

  实现该<xref:System.ComponentModel.IListSource>接口的类启用了对非列表对象的基于列表的绑定。 的<xref:System.ComponentModel.IListSource.GetList%2A> <xref:System.Collections.IList>方法用于从不从继承的对象中返回可绑定列表。 <xref:System.ComponentModel.IListSource> <xref:System.ComponentModel.IListSource>由<xref:System.Data.DataSet>类使用。

- <xref:System.ComponentModel.IRaiseItemChangedEvents>交互

  实现<xref:System.ComponentModel.IRaiseItemChangedEvents>接口的类是一个同时<xref:System.ComponentModel.IBindingList>实现接口的可绑定列表。 此接口用于指示类型是否通过其<xref:System.ComponentModel.IBindingList.ListChanged> <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>属性引发类型<xref:System.ComponentModel.ListChangedType.ItemChanged>的事件。

  > [!NOTE]
  > <xref:System.ComponentModel.IRaiseItemChangedEvents>如果你的数据源提供了前面所述的属性以列出事件转换，并且<xref:System.Windows.Forms.BindingSource>与组件交互，则应实现。 否则， <xref:System.Windows.Forms.BindingSource>还将执行属性以列出事件转换，从而降低性能。

- <xref:System.ComponentModel.ISupportInitialize>交互

  实现<xref:System.ComponentModel.ISupportInitialize>接口的组件利用批处理优化的优点来设置属性和初始化依赖属性。 <xref:System.ComponentModel.ISupportInitialize>包含两个方法：

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>发出对象初始化正在启动的信号。

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>通知对象初始化已完成。

- <xref:System.ComponentModel.ISupportInitializeNotification>交互

  实现<xref:System.ComponentModel.ISupportInitializeNotification>接口的组件还<xref:System.ComponentModel.ISupportInitialize>实现接口。 此接口允许通知其他<xref:System.ComponentModel.ISupportInitialize>组件初始化已完成。 此<xref:System.ComponentModel.ISupportInitializeNotification>接口包含两个成员：

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>返回一个`boolean`值，该值指示组件是否已初始化。

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>当<xref:System.ComponentModel.ISupportInitialize.EndInit%2A>调用时发生。

- <xref:System.ComponentModel.INotifyPropertyChanged>交互

  实现此接口的类是一个在其任何属性值更改时都会引发事件的类型。 此接口旨在替换控件的每个属性都有一个更改事件这种模式。 当在<xref:System.ComponentModel.BindingList%601>中使用时，业务对象应<xref:System.ComponentModel.INotifyPropertyChanged>实现接口，system.componentmodel.bindinglist\`1 会将事件转换<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>为<xref:System.ComponentModel.BindingList%601.ListChanged>类型<xref:System.ComponentModel.ListChangedType.ItemChanged>为的事件。

  > [!NOTE]
  > 若要在绑定的客户端和数据源之间的绑定中发生更改通知，绑定数据源类型应实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口（首选），也可以为绑定类型提供*propertyName*`Changed` 事件，但你不应同时执行这两项操作。

### <a name="interfaces-for-implementation-by-component-authors"></a>要由组件作者实现的接口

下列接口设计为由 Windows 窗体数据绑定引擎使用：

- <xref:System.Windows.Forms.IBindableComponent>交互

  实现此接口的类是支持数据绑定的非控件组件。 此类通过<xref:System.Windows.Forms.IBindableComponent.DataBindings%2A>此接口的和<xref:System.Windows.Forms.IBindableComponent.BindingContext%2A>属性返回组件的数据绑定和绑定上下文。

  > [!NOTE]
  > 如果组件继承自<xref:System.Windows.Forms.Control>，则无需<xref:System.Windows.Forms.IBindableComponent>实现接口。

- <xref:System.Windows.Forms.ICurrencyManagerProvider>交互

  实现<xref:System.Windows.Forms.ICurrencyManagerProvider>接口的类是一个组件，它提供自己<xref:System.Windows.Forms.CurrencyManager>的来管理与此特定组件关联的绑定。 对自定义<xref:System.Windows.Forms.CurrencyManager>的访问<xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>由属性提供。

  > [!NOTE]
  > 继承自<xref:System.Windows.Forms.Control>的类通过其<xref:System.Windows.Forms.Control.BindingContext%2A>属性自动管理绑定，因此你需要实现的<xref:System.Windows.Forms.ICurrencyManagerProvider>情况非常少见。

## <a name="see-also"></a>请参阅

- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
- [如何：在 Windows 窗体 @ no__t 上创建简单绑定控件
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
