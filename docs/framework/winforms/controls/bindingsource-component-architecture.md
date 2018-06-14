---
title: BindingSource 组件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: b0334bd7a0bc5ff46c43fd7ee549422d98c35efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529255"
---
# <a name="bindingsource-component-architecture"></a>BindingSource 组件体系结构
与<xref:System.Windows.Forms.BindingSource>组件时，普遍，你可以将所有 Windows 窗体控件都绑定到数据源。  
  
 <xref:System.Windows.Forms.BindingSource>组件简化将控件绑定到数据源的过程，并通过传统数据绑定有以下优点：  
  
-   使设计时绑定到业务对象。  
  
-   封装<xref:System.Windows.Forms.CurrencyManager>功能，并公开<xref:System.Windows.Forms.CurrencyManager>在设计时的事件。  
  
-   简化了创建支持列表<xref:System.ComponentModel.IBindingList>通过提供列表更改通知，本质上不支持列表的数据源更改通知的接口。  
  
-   提供的一个扩展点<xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType>方法。  
  
-   提供数据源和控件之间的间接级别。 当在运行时可更改数据源时，这种间接方式很重要。  
  
-   专门与其他数据相关的 Windows 窗体控件，互操作<xref:System.Windows.Forms.BindingNavigator>和<xref:System.Windows.Forms.DataGridView>控件。  
  
 出于这些原因，<xref:System.Windows.Forms.BindingSource>组件是将 Windows 窗体控件绑定到数据源的首选的方法。  
  
## <a name="bindingsource-features"></a>BindingSource 功能  
 <xref:System.Windows.Forms.BindingSource>组件提供了一些功能，为控件绑定到数据。 通过这些功能，你可以实现与几乎无需进行编码您的大多数数据绑定方案。  
  
 <xref:System.Windows.Forms.BindingSource>组件完成此操作通过用于访问许多不同类型的数据源提供一致的接口。 这意味着到任何类型的绑定使用相同的过程。 例如，你可以附加<xref:System.Windows.Forms.BindingSource.DataSource%2A>属性<xref:System.Data.DataSet>或业务对象与两种情况下使用的相同的一套属性、 方法和事件来操作数据源。  
  
 一致的接口提供<xref:System.Windows.Forms.BindingSource>组件极大地简化了将数据绑定到控件的过程。 为提供的数据源类型的更改通知，<xref:System.Windows.Forms.BindingSource>组件自动通信控件和数据源之间的更改。 对于不提供更改通知的数据源类型，事件会提供能够让你引发更改通知。 以下列表显示了支持的功能<xref:System.Windows.Forms.BindingSource>组件：  
  
-   间接寻址。  
  
-   货币管理。  
  
-   作为列表的数据源。  
  
-   <xref:System.Windows.Forms.BindingSource> 作为<xref:System.ComponentModel.IBindingList>。  
  
-   创建自定义项。  
  
-   创建事务性项。  
  
-   <xref:System.Collections.IEnumerable> 支持。  
  
-   设计时支持。  
  
-   静态<xref:System.Windows.Forms.ListBindingHelper>方法。  
  
-   排序和筛选与<xref:System.ComponentModel.IBindingListView>接口。  
  
-   与集成<xref:System.Windows.Forms.BindingNavigator>。  
  
### <a name="indirection"></a>间接寻址  
 <xref:System.Windows.Forms.BindingSource>组件提供一定程度的间接性控件与数据源之间。 而不是将控件绑定到数据源的直接，你将控件绑定到<xref:System.Windows.Forms.BindingSource>，并附加到的数据源<xref:System.Windows.Forms.BindingSource>组件的<xref:System.Windows.Forms.BindingSource.DataSource%2A>属性。  
  
 使用此级别的间接寻址，你可以更改数据源，而重置控件绑定。 这为你提供以下功能：  
  
-   你可以将附加<xref:System.Windows.Forms.BindingSource>到不同的数据源时保留当前的控件绑定。  
  
-   你可以更改数据源中的项，并通知绑定的控件。 有关详细信息，请参阅[如何： 使用 BindingSource Windows 窗体控件中反映数据源更新](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)。  
  
-   可以将绑定到<xref:System.Type>而不是内存中的对象。 有关详细信息，请参阅[如何： 将 Windows 窗体控件绑定到类型](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)。 你可以随后绑定到的对象在运行时。  
  
### <a name="currency-management"></a>当前项管理  
 <xref:System.Windows.Forms.BindingSource>组件实现<xref:System.Windows.Forms.ICurrencyManagerProvider>处理货币管理为你的接口。 与<xref:System.Windows.Forms.ICurrencyManagerProvider>接口，你还可以访问的货币管理器<xref:System.Windows.Forms.BindingSource>，另一个的货币管理器除了<xref:System.Windows.Forms.BindingSource>绑定到同一<xref:System.Windows.Forms.BindingSource.DataMember%2A>。  
  
 <xref:System.Windows.Forms.BindingSource>组件封装<xref:System.Windows.Forms.CurrencyManager>功能，并公开了最常用<xref:System.Windows.Forms.CurrencyManager>属性和事件。 下表介绍一些与货币管理相关的成员。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 属性  
 获取与关联的货币管理器<xref:System.Windows.Forms.BindingSource>。  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> 方法  
 如果没有另一个<xref:System.Windows.Forms.BindingSource>绑定到指定的数据成员，请获取其流量管理器。  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> 属性  
 获取数据源的当前项。  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性  
 获取或设置基础列表中的当前位置。  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 方法  
 将挂起的更改应用于基础数据源。  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 方法  
 取消当前的编辑操作。  
  
### <a name="data-source-as-a-list"></a>作为列表的数据源  
 <xref:System.Windows.Forms.BindingSource>组件实现<xref:System.ComponentModel.IBindingListView>和<xref:System.ComponentModel.ITypedList>接口。 与此实现中，你可以使用<xref:System.Windows.Forms.BindingSource>组件自身作为数据源，而无需任何外部存储。  
  
 当<xref:System.Windows.Forms.BindingSource>组件连接到数据源，它公开作为列表的数据源。  
  
 <xref:System.Windows.Forms.BindingSource.DataSource%2A>属性可以设置为几个数据源。 其中包括类型、 对象和类型的列表。 产生的数据源将公开为一个列表。 下表显示了一些常见的数据源和生成的列表计算。  
  
|数据源属性|列表结果|  
|-------------------------|------------------|  
|空引用（在 Visual Basic 中为 `Nothing`）|一个空<xref:System.ComponentModel.IBindingList>的对象。 将项添加到所添加项的类型设置的列表。|  
|空引用 (`Nothing`在 Visual Basic 中) 与<xref:System.Windows.Forms.BindingSource.DataMember%2A>设置|不支持;引发<xref:System.ArgumentException>。|  
|非列表类型或者"T"类型的对象|一个空<xref:System.ComponentModel.IBindingList>的"T"类型。|  
|数组实例|<xref:System.ComponentModel.IBindingList>包含数组元素。|  
|<xref:System.Collections.IEnumerable> 实例|<xref:System.ComponentModel.IBindingList>包含<xref:System.Collections.IEnumerable>项|  
|列出"T"的包含类型的实例|<xref:System.ComponentModel.IBindingList>包含"T"类型的实例。|  
  
 此外，<xref:System.Windows.Forms.BindingSource.DataSource%2A>可以设置为其他列表类型，如<xref:System.ComponentModel.IListSource>和<xref:System.ComponentModel.ITypedList>，和<xref:System.Windows.Forms.BindingSource>将适当地处理。 在这种情况下，列表中包含该类型应具有默认构造函数。  
  
### <a name="bindingsource-as-an-ibindinglist"></a>作为 IBindingList BindingSource  
 <xref:System.Windows.Forms.BindingSource>组件提供用于访问和操作作为基础数据成员<xref:System.ComponentModel.IBindingList>。 下表描述了其中几个成员。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> 属性|获取来自计算的结果的列表<xref:System.Windows.Forms.BindingSource.DataSource%2A>或<xref:System.Windows.Forms.BindingSource.DataMember%2A>属性。|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> 方法|在基础列表中添加一个新项。 适用于实现的数据源<xref:System.ComponentModel.IBindingList>接口，并允许添加项 (即，<xref:System.Windows.Forms.BindingSource.AllowNew%2A>属性设置为`true`)。|  
  
### <a name="custom-item-creation"></a>创建自定义项  
 你可以处理<xref:System.Windows.Forms.BindingSource.AddingNew>事件，以便提供你自己的项创建逻辑。 <xref:System.Windows.Forms.BindingSource.AddingNew>事件发生在新对象添加到之前<xref:System.Windows.Forms.BindingSource>。 之后，将引发此事件<xref:System.Windows.Forms.BindingSource.AddNew%2A>调用方法，但之前对基础列表添加新项。 通过处理此事件，则可以提供自定义项创建行为，而不必从派生<xref:System.Windows.Forms.BindingSource>类。 有关详细信息，请参阅[如何： 使用 Windows 窗体 BindingSource 自定义项添加](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)。  
  
### <a name="transactional-item-creation"></a>创建事务性项  
 <xref:System.Windows.Forms.BindingSource>组件实现<xref:System.ComponentModel.ICancelAddNew>接口，可创建事务的项。 通过使用调用临时创建一个新项后<xref:System.Windows.Forms.BindingSource.AddNew%2A>，可能会提交或回滚通过以下方式添加：  
  
-   <xref:System.ComponentModel.ICancelAddNew.EndNew%2A>方法显式提交挂起的添加。  
  
-   执行另一个集合操作，如插入、 移除或移动，将隐式提交挂起的添加。  
  
-   <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>方法将回滚挂起的新如果方法不已提交。  
  
### <a name="ienumerable-support"></a>IEnumerable 支持  
 <xref:System.Windows.Forms.BindingSource>组件，将控件绑定到<xref:System.Collections.IEnumerable>数据源。 与此组件，你可以将绑定到数据源如<xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>。  
  
 当<xref:System.Collections.IEnumerable>数据源分配给<xref:System.Windows.Forms.BindingSource>组件，<xref:System.Windows.Forms.BindingSource>创建<xref:System.ComponentModel.IBindingList>，并将添加的内容<xref:System.Collections.IEnumerable>到列表的数据源。  
  
### <a name="design-time-support"></a>设计时支持  
 某些对象类型不能在设计时，例如从工厂类，创建的对象或 Web 服务返回的对象创建。 即使在你的控件可以绑定到的内存中没有任何对象，您有时需要在设计时，将控件绑定到这些类型。 例如，可能需要标签的列标题<xref:System.Windows.Forms.DataGridView>控件替换你自定义类型的公共属性的名称。  
  
 若要支持此方案中，<xref:System.Windows.Forms.BindingSource>组件支持绑定到<xref:System.Type>。 当分配<xref:System.Type>到<xref:System.Windows.Forms.BindingSource.DataSource%2A>属性，<xref:System.Windows.Forms.BindingSource>组件创建一个空<xref:System.ComponentModel.BindingList%601>的<xref:System.Type>项。 你随后将绑定到任何控件<xref:System.Windows.Forms.BindingSource>在设计时或在运行时，将与属性或类型的架构存在收到警报的组件。 有关详细信息，请参阅[如何： 将 Windows 窗体控件绑定到类型](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)。  
  
### <a name="static-listbindinghelper-methods"></a>静态 ListBindingHelper 方法  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>， <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>，和<xref:System.Windows.Forms.BindingSource>类型所有的共享通用逻辑，以生成从列表`DataSource` / `DataMember`对。 此外，此公共逻辑公开以供控件作者和其他第三方在下列`static`方法：  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>。  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>排序和筛选与 IBindingListView 接口  
 <xref:System.Windows.Forms.BindingSource>组件实现<xref:System.ComponentModel.IBindingListView>接口，该扩展接口<xref:System.ComponentModel.IBindingList>接口。 <xref:System.ComponentModel.IBindingList>提供单个列排序和<xref:System.ComponentModel.IBindingListView>提供高级排序和筛选。 与<xref:System.ComponentModel.IBindingListView>、 可以进行排序和筛选器项在数据源，如果数据源还实现这些接口之一。 <xref:System.Windows.Forms.BindingSource>组件不提供这些成员的引用实现。 相反，将调用转发给基础列表。  
  
 下表介绍用于排序和筛选的属性。  
  
|成员|描述|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> 属性|如果数据源是 <xref:System.ComponentModel.IBindingListView>，则获取或设置用于筛选已查看的行的表达式。|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> 属性|如果数据源是 <xref:System.ComponentModel.IBindingList>，则获取或设置用于排序的列名称并对顺序信息进行排序。<br /><br /> -或-<br /><br /> 如果数据源是<xref:System.ComponentModel.IBindingListView>并支持高级排序，则获取用于排序和排序顺序的多个列名称|  
  
### <a name="integration-with-bindingnavigator"></a>与 BindingNavigator 的集成  
 你可以使用<xref:System.Windows.Forms.BindingSource>组件将任何 Windows 窗体控件绑定到数据源，但<xref:System.Windows.Forms.BindingNavigator>控件专门用于处理<xref:System.Windows.Forms.BindingSource>组件。 <xref:System.Windows.Forms.BindingNavigator>控件提供用户界面，用于控制<xref:System.Windows.Forms.BindingSource>组件的当前项。 默认情况下，<xref:System.Windows.Forms.BindingNavigator>控件提供对应的导航方法的按钮<xref:System.Windows.Forms.BindingSource>组件。 有关详细信息，请参阅[如何： 使用 Windows 窗体 BindingNavigator 控件导航数据](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [BindingSource 组件概述](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [BindingNavigator 控件](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [如何：将 Windows 窗体控件绑定到类型](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
