---
title: WPF 버전 4.5의 새로운 기능
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 8eff8da7746047c450b2e23af63d43b13f3b970c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746930"
---
# <a name="whats-new-in-wpf-version-45"></a>WPF 버전 4.5의 새로운 기능
<a name="introduction"></a>本主题包含有关 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 版本4.5 中的新增功能和增强功能的信息。  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
- [리본 컨트롤](#ribbon_control)  
  
- [그룹화된 큰 데이터 집합을 표시할 때의 성능 개선](#grouped_virtualization)  
  
- [VirtualizingPanel의 새로운 기능](#VirtualizingPanel)  
  
- [정적 속성에 바인딩](#static_properties)  
  
- [UI가 아닌 스레드에서 컬렉션 액세스](#xthread_access)  
  
- [동기적 및 비동기적으로 데이터 유효성 검사](#INotifyDataErrorInfo)  
  
- [데이터 바인딩 원본을 자동으로 업데이트](#delay)  
  
- [ICustomTypeProvider를 구현하는 형식에 바인딩](#ICustomTypeProvider)  
  
- [바인딩 식에서 데이터 바인딩 정보 검색](#binding_state)  
  
- [유효한 DataContext 개체 확인](#DisconnectedSource)  
  
- [데이터 값이 변경될 때 데이터의 위치 변경(라이브 셰이핑)](#live_shaping)  
  
- [이벤트에 대한 약한 참조 설정을 위한 지원 개선](#weak_event_pattern)  
  
- [Dispatcher 클래스에 대한 새로운 메서드](#async)  
  
- [이벤트에 대한 태그 확장](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>리본 컨트롤  
 WPF 4.5 附带了一个承载快速访问工具栏、应用程序菜单和选项卡的 <xref:System.Windows.Controls.Ribbon.Ribbon> 控件。  자세한 내용은 [리본 개요](/visualstudio/vsto/ribbon-overview)를 참조하세요.  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>그룹화된 큰 데이터 집합을 표시할 때의 성능 개선  
 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 사용자 인터페이스(UI) 요소의 하위 집합이 생성될 때 UI 가상화가 발생합니다. <xref:System.Windows.Controls.VirtualizingPanel> 定义了 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 附加属性，该属性可用于分组数据的 UI 虚拟化。  데이터 그룹화에 대한 자세한 내용은 방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화를 참조하세요.  有关虚拟分组数据的详细信息，请参阅 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 附加属性。  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>VirtualizingPanel의 새로운 기능  
  
1. 您可以使用 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 附加属性指定 <xref:System.Windows.Controls.VirtualizingPanel>（如 <xref:System.Windows.Controls.VirtualizingStackPanel>）是否显示部分项。 如果 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 设置为 <xref:System.Windows.Controls.ScrollUnit.Item>，则 <xref:System.Windows.Controls.VirtualizingPanel> 将只显示完全可见的项。 如果 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 设置为 <xref:System.Windows.Controls.ScrollUnit.Pixel>，则 <xref:System.Windows.Controls.VirtualizingPanel> 可显示部分可见项。  
  
2. 使用 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> 附加属性对 <xref:System.Windows.Controls.VirtualizingPanel> 进行虚拟化时，可以指定视区之前和之后的缓存大小。  캐시는 항목이 가상화되지 않는 뷰포트 위 또는 아래 공간 양입니다.  캐시를 사용하면 뷰로 스크롤하는 동안 UI 요소가 생성되지 않도록 하여 성능을 향상시킬 수 있습니다. 캐시는 낮은 우선 순위에서 채워지므로 작업 중에는 애플리케이션이 응답하지 않게 됩니다. <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> 属性确定 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>使用的度量单位。  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>정적 속성에 바인딩  
 데이터 바인딩 원본으로 정적 속성을 사용할 수 있습니다. 데이터 바인딩 엔진은 정적 이벤트가 발생할 경우 속성 값이 변경되는 것을 인식합니다.  예를 들어 `SomeClass` 클래스가 `MyProperty`라는 정적 속성을 정의하는 경우 `SomeClass`는 `MyProperty` 값이 변경될 때 발생하는 정적 이벤트를 정의할 수 있습니다.  정적 이벤트는 다음 서명 중 하나를 사용할 수 있습니다.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 请注意，在第一种情况下，类公开了一个名为*PropertyName*`Changed` 的静态事件，该事件将 <xref:System.EventArgs> 传递到事件处理程序。  在第二种情况下，类公开名为 `StaticPropertyChanged` 的静态事件，该事件将 <xref:System.ComponentModel.PropertyChangedEventArgs> 传递到事件处理程序。 정적 속성을 구현하는 클래스에서 두 메서드 중 하나를 사용하여 속성-변경 알림이 발생하도록 선택할 수 있습니다.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>UI가 아닌 스레드에서 컬렉션 액세스  
 WPF를 사용하면 컬렉션을 만들지 않은 스레드에서 데이터 컬렉션을 액세스하고 수정할 수 있습니다.  이를 통해 데이터베이스와 같은 외부 원본에서 데이터를 수신하는 데 백그라운드 스레드를 사용하고 UI 스레드에 데이터를 표시할 수 있습니다.  다른 스레드를 사용하여 콜렉션을 수정하면 사용자 인터페이스는 사용자 상호 작용에 응답성을 유지합니다.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>동기적 및 비동기적으로 데이터 유효성 검사  
 <xref:System.ComponentModel.INotifyDataErrorInfo> 接口允许数据实体类实现自定义验证规则，并以异步方式公开验证结果。 또한 이 인터페이스는 사용자 지정 오류 개체, 속성당 여러 오류, 속성 간 오류 및 엔터티 수준 오류도 지원합니다.  자세한 내용은 <xref:System.ComponentModel.INotifyDataErrorInfo>를 참조하세요.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>데이터 바인딩 원본을 자동으로 업데이트  
 如果使用数据绑定来更新数据源，则可以使用 <xref:System.Windows.Data.BindingBase.Delay%2A> 属性指定在源更新之前目标上的属性更改后要传递的时间量。  例如，假设您有一个 <xref:System.Windows.Controls.Slider>，它 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 属性数据双向绑定到数据对象的属性，<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性设置为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。  在此示例中，当用户移动 <xref:System.Windows.Controls.Slider>时，<xref:System.Windows.Controls.Slider> 移动的每个像素的源将进行更新。  仅当滑块的 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 停止变化时，源对象才需要滑块的值。  若要防止过于频繁地更新源，请使用 <xref:System.Windows.Data.BindingBase.Delay%2A> 指定在拇指停止移动后一定时间段过后不应更新源。  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>ICustomTypeProvider를 구현하는 형식에 바인딩  
 WPF 支持对实现 <xref:System.Reflection.ICustomTypeProvider>（也称为自定义类型）的对象进行数据绑定。  다음과 같은 경우 사용자 지정 형식을 사용할 수 있습니다.  
  
1. 作为数据绑定中的 <xref:System.Windows.PropertyPath>。 例如，<xref:System.Windows.Data.Binding> 的 <xref:System.Windows.Data.Binding.Path%2A> 属性可以引用自定义类型的属性。  
  
2. 作为 <xref:System.Windows.DataTemplate.DataType%2A> 属性的值。  
  
3. 一种类型，用于确定 <xref:System.Windows.Controls.DataGrid>中自动生成的列。  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>바인딩 식에서 데이터 바인딩 정보 검색  
 在某些情况下，你可能会获取 <xref:System.Windows.Data.Binding> 的 <xref:System.Windows.Data.BindingExpression>，并需要有关绑定的源和目标对象的信息。  원본 또는 대상 개체나 연결된 속성을 얻도록 새로운 API가 추가되었습니다.  如果有 <xref:System.Windows.Data.BindingExpression>，请使用以下 Api 获取有关目标和源的信息。  
  
|바인딩의 다음 값을 찾으려면|다음 API 사용|  
|---------------------------------------|------------------|  
|대상 개체|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|대상 속성|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|소스 개체|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|원본 속성|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Data.BindingExpression> 是否属于 <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Data.BindingGroup> 的所有者|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>유효한 DataContext 개체 확인  
 有些情况下，<xref:System.Windows.Controls.ItemsControl> 中的项容器 <xref:System.Windows.FrameworkElement.DataContext%2A> 会断开连接。  项容器是在 <xref:System.Windows.Controls.ItemsControl>中显示项的 UI 元素。  当 <xref:System.Windows.Controls.ItemsControl> 被数据绑定到集合时，将为每个项生成项容器。 경우에 따라 항목 컨테이너는 시각적 트리에서 제거됩니다. 删除项容器的两种典型情况是：从基础集合中删除项时，以及何时在 <xref:System.Windows.Controls.ItemsControl>上启用虚拟化。 在这些情况下，项容器的 <xref:System.Windows.FrameworkElement.DataContext%2A> 属性将设置为 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> 静态属性返回的 sentinel 对象。  在访问项容器的 <xref:System.Windows.FrameworkElement.DataContext%2A> 之前，应检查 <xref:System.Windows.FrameworkElement.DataContext%2A> 是否等于 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> 对象。  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>데이터 값이 변경될 때 데이터의 위치 변경(라이브 셰이핑)  
 데이터의 컬렉션을 그룹화, 정렬 또는 필터링할 수 있습니다. WPF 4.5에서는 데이터가 수정되면 데이터를 다시 배열할 수 있습니다. 예를 들어, 애플리케이션에서 사용 하는 <xref:System.Windows.Controls.DataGrid> 따라 주식 시장에 주식, 주식을 나열 하려면 정렬 합니다. 如果在股票的 <xref:System.Windows.Data.CollectionView>上启用实时排序，则当股票的值变大或小于另一个股票的值时，股票的 <xref:System.Windows.Controls.DataGrid> 位置会移动。   有关详细信息，请参阅 <xref:System.ComponentModel.ICollectionViewLiveShaping> 接口。  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>이벤트에 대한 약한 참조 설정을 위한 지원 개선  
 이벤트 구독자가 추가 인터페이스 구현 없이 참여할 수 있으므로 약한 이벤트 패턴을 구현하기가 더 쉬워졌습니다.  泛型 <xref:System.Windows.WeakEventManager> 类还允许订阅服务器参与弱事件模式（如果特定事件不存在专用 <xref:System.Windows.WeakEventManager>）。  자세한 내용은 [약한 이벤트 패턴](../advanced/weak-event-patterns.md)을 참조하세요.  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Dispatcher 클래스에 대한 새로운 메서드  
 Dispatcher 클래스는 동기 및 비동기 작업에 대해 새로운 메서드를 정의합니다.  同步 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 方法定义采用 <xref:System.Action> 或 <xref:System.Func%601> 参数的重载。 新的异步方法 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>还采用 <xref:System.Action> 或 <xref:System.Func%601> 作为回调参数，并返回 <xref:System.Windows.Threading.DispatcherOperation> 或 <xref:System.Windows.Threading.DispatcherOperation%601>。   <xref:System.Windows.Threading.DispatcherOperation> 和 <xref:System.Windows.Threading.DispatcherOperation%601> 类定义 <xref:System.Threading.Tasks.Task> 属性。  调用 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>时，可以将 `await` 关键字与 <xref:System.Windows.Threading.DispatcherOperation> 或关联的 <xref:System.Threading.Tasks.Task>一起使用。 如果需要同步等待 <xref:System.Windows.Threading.DispatcherOperation> 或 <xref:System.Windows.Threading.DispatcherOperation%601>返回的 <xref:System.Threading.Tasks.Task>，请调用 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 扩展方法。 如果操作在调用线程上排队，则调用 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 会导致死锁。 有关使用 <xref:System.Threading.Tasks.Task> 执行异步操作的详细信息，请参阅[任务并行（任务并行库）](../../../standard/parallel-programming/task-based-asynchronous-programming.md)。  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>이벤트에 대한 태그 확장  
 WPF 4.5에서는 이벤트에 대한 태그 확장을 지원합니다.  WPF는 이벤트에 사용될 태그 확장을 정의하지 않지만 타사에서 이벤트에 사용할 수 있는 태그 확장을 만들 수 있습니다.  
  
## <a name="see-also"></a>另请参阅

- [.NET Framework의 새로운 기능](../../whats-new/index.md)
