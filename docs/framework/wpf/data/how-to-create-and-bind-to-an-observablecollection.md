---
title: 如何：创建和绑定到 ObservableCollection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: cf9f714878cd1b0b179dc1ced44e3dcfe7c2f9bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517586"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a><span data-ttu-id="690f8-102">如何：创建和绑定到 ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="690f8-102">How to: Create and Bind to an ObservableCollection</span></span>
<span data-ttu-id="690f8-103">此示例演示如何创建和绑定到一个集合，其中派生<xref:System.Collections.ObjectModel.ObservableCollection%601>类，该类是一个集合类，添加或移除项时提供通知。</span><span class="sxs-lookup"><span data-stu-id="690f8-103">This example shows how to create and bind to a collection that derives from the <xref:System.Collections.ObjectModel.ObservableCollection%601> class, which is a collection class that provides notifications when items get added or removed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="690f8-104">示例</span><span class="sxs-lookup"><span data-stu-id="690f8-104">Example</span></span>  
 <span data-ttu-id="690f8-105">下面的示例演示 `NameList` 集合的实现：</span><span class="sxs-lookup"><span data-stu-id="690f8-105">The following example shows the implementation of a `NameList` collection:</span></span>  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 <span data-ttu-id="690f8-106">可以根据[使数据可用于 XAML 中的绑定](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)中的说明，按照与其他 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 对象相同的方式使集合可用于绑定。</span><span class="sxs-lookup"><span data-stu-id="690f8-106">You can make the collection available for binding the same way you would with other [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects, as described in [Make Data Available for Binding in XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).</span></span> <span data-ttu-id="690f8-107">例如，可以在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中实例化该集合，并将该集合指定为一个资源，如下所示：</span><span class="sxs-lookup"><span data-stu-id="690f8-107">For example, you can instantiate the collection in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and specify the collection as a resource, as shown here:</span></span>  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 <span data-ttu-id="690f8-108">然后可以绑定到该集合：</span><span class="sxs-lookup"><span data-stu-id="690f8-108">You can then bind to the collection:</span></span>  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 <span data-ttu-id="690f8-109">此处没有显示 `NameItemTemplate` 的定义。</span><span class="sxs-lookup"><span data-stu-id="690f8-109">The definition of `NameItemTemplate` is not shown here.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="690f8-110">集合中的对象必须满足[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)中所述的要求。</span><span class="sxs-lookup"><span data-stu-id="690f8-110">The objects in your collection must satisfy the requirements described in the [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span> <span data-ttu-id="690f8-111">具体而言，如果使用的<xref:System.Windows.Data.BindingMode.OneWay>或<xref:System.Windows.Data.BindingMode.TwoWay>(例如，希望你[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]时更新源属性发生显著变化)，必须实现适当的属性更改通知机制，如<xref:System.ComponentModel.INotifyPropertyChanged>接口。</span><span class="sxs-lookup"><span data-stu-id="690f8-111">In particular, if you are using <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> (for example, you want your [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to update when the source properties change dynamically), you must implement a suitable property changed notification mechanism such as the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span>  
  
 <span data-ttu-id="690f8-112">有关详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)中的“绑定到集合”一节。</span><span class="sxs-lookup"><span data-stu-id="690f8-112">For more information, see the Binding to Collections section in the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690f8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="690f8-113">See also</span></span>
- [<span data-ttu-id="690f8-114">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="690f8-114">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="690f8-115">在视图中筛选数据</span><span class="sxs-lookup"><span data-stu-id="690f8-115">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="690f8-116">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="690f8-116">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="690f8-117">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="690f8-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="690f8-118">帮助主题</span><span class="sxs-lookup"><span data-stu-id="690f8-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
