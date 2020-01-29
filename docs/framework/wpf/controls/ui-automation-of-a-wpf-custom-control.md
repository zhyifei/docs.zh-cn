---
title: 自定义控件的 UI 自动化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: a370ed2c6b1f3273eca93b4865a032e8299f1cfb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738196"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>WPF 사용자 지정 컨트롤의 UI 자동화
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]에서는 자동화 클라이언트가 다양한 플랫폼 및 프레임워크의 사용자 인터페이스를 검사하거나 운영하는 데 사용할 수 있는 일반화된 단일 인터페이스를 제공합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 통해 품질 보증(테스트) 코드 및 화면 읽기 프로그램과 같은 접근성 애플리케이션은 사용자 인터페이스 요소를 검사하고 다른 코드에서 해당 요소에 대한 사용자 상호 작용을 시뮬레이트할 수 있습니다. 모든 플랫폼에서 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 자세한 내용은 접근성을 참조하세요.  
  
 이 항목에서는 WPF 애플리케이션에서 실행되는 사용자 지정 컨트롤에 대한 서버 쪽 UI 자동화 공급자를 구현하는 방법을 설명합니다. WPF는 사용자 인터페이스 요소의 트리에 대응하는 피어 자동화 개체의 트리를 통해 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 지원합니다. 접근성 기능을 제공하는 애플리케이션 및 테스트 코드는 자동화 피어 개체를 직접 사용(in-process 코드의 경우)하거나 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에서 제공하는 일반화된 인터페이스를 통해 사용할 수 있습니다.  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>자동화 피어 클래스  
 WPF 控件支持通过派生自 <xref:System.Windows.Automation.Peers.AutomationPeer>的对等类树 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]。 규칙에 따라 피어 클래스 이름은 컨트롤 클래스 이름으로 시작하고 "AutomationPeer"로 끝납니다. 例如，<xref:System.Windows.Automation.Peers.ButtonAutomationPeer> 是 <xref:System.Windows.Controls.Button> 控件类的对等类。 对等类大致等效于 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 控件类型，但特定于 WPF 元素。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 인터페이스를 통해 WPF 애플리케이션에 액세스하는 자동화 코드는 자동화 피어를 직접 사용하지 않지만 동일한 프로세스 공간의 자동화 코드는 자동화 피어를 직접 사용할 수 있습니다.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>기본 제공 자동화 피어 클래스  
 요소는 사용자의 인터페이스 작업을 허용하는 경우 또는 화면 읽기 프로그램 애플리케이션 사용자에게 필요한 정보를 포함하는 경우 자동화 피어 클래스를 구현합니다. 일부 WPF 시각적 요소에는 자동화 피어가 없습니다. 实现自动化对等方的类的示例包括 <xref:System.Windows.Controls.Button>、<xref:System.Windows.Controls.TextBox>和 <xref:System.Windows.Controls.Label>。 不实现自动化对等类的类的示例是派生自 <xref:System.Windows.Controls.Decorator>的类，如 <xref:System.Windows.Controls.Border>，以及基于 <xref:System.Windows.Controls.Panel>的类，如 <xref:System.Windows.Controls.Grid> 和 <xref:System.Windows.Controls.Canvas>。  
  
 基 <xref:System.Windows.Controls.Control> 类没有相应的对等类。 如果需要对等类对应于从 <xref:System.Windows.Controls.Control>派生的自定义控件，则应从 <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>派生自定义对等类。  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>파생된 피어의 보안 고려 사항  
 자동화 피어는 부분 신뢰 환경에서 실행되어야 합니다. UIAutomationClient 어셈블리의 코드는 부분 신뢰 환경에서 실행되도록 구성되지 않았으며 자동화 피어 코드는 해당 어셈블리를 참조해서는 안 됩니다. 대신 UIAutomationTypes 어셈블리의 클래스를 사용해야 합니다. 例如，应使用 Uiautomationtypes.dll 程序集中的 <xref:System.Windows.Automation.AutomationElementIdentifiers> 类，该程序集对应于 Uiautomationclient.dll 程序集中的 <xref:System.Windows.Automation.AutomationElement> 类。 자동화 피어 코드에서 UIAutomationTypes 어셈블리를 참조해도 안전합니다.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>피어 탐색  
 定位自动化对等节点后，进程内代码可以通过调用对象的 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> 和 <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> 方法来导航对等树。 在控件内的 WPF 元素间导航受 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> 方法的对等实现的支持。 UI 자동화 시스템은 이 메서드를 호출하여 컨트롤 내에 포함된 하위 요소의 트리를 작성합니다(예: 목록 상자의 목록 항목). 默认 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> 方法遍历元素的可视化树，以生成自动化对等方的树。 사용자 지정 컨트롤은 자식 요소를 자동화 클라이언트에 노출하도록 이 메서드를 재정의하여 정보를 전달하거나 사용자 상호 작용을 허용하는 요소의 자동화 피어를 반환합니다.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>파생된 피어의 사용자 지정  
 派生自 <xref:System.Windows.UIElement> 和 <xref:System.Windows.ContentElement> 的所有类都包含受保护的虚拟方法 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>。 WPF 调用 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 为每个控件获取自动化对等对象。 자동화 코드는 피어를 사용하여 컨트롤의 특성 및 기능에 대한 정보를 가져오고 대화형 사용을 시뮬레이트할 수 있습니다. 支持自动化的自定义控件必须重写 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 并返回从 <xref:System.Windows.Automation.Peers.AutomationPeer>派生的类的实例。 例如，如果自定义控件派生自 <xref:System.Windows.Controls.Primitives.ButtonBase> 类，则 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 返回的对象应派生自 <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>。  
  
 사용자 지정 컨트롤을 구현할 때 사용자 지정 컨트롤과 관련된 고유한 동작을 설명하는 "Core" 메서드를 기본 자동화 피어 클래스에서 재정의해야 합니다.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer 재정의  
 重写自定义控件的 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 方法，使其返回必须直接或间接从 <xref:System.Windows.Automation.Peers.AutomationPeer>派生的提供程序对象。  
  
### <a name="override-getpattern"></a>GetPattern 재정의  
 자동화 피어는 서버 쪽 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 공급자의 몇 가지 구현 측면을 간소화하지만 사용자 지정 컨트롤 자동화 피어는 패턴 인터페이스를 계속 처리해야 합니다. 与非 WPF 提供程序一样，对等方支持控件模式，方法是在 <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> 命名空间中提供接口的实现，如 <xref:System.Windows.Automation.Provider.IInvokeProvider>。 컨트롤 패턴 인터페이스는 피어 자체 또는 다른 개체를 통해 구현할 수 있습니다. 的对等的 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 返回支持指定模式的对象。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 代码调用 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 方法并指定 <xref:System.Windows.Automation.Peers.PatternInterface> 枚举值。 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 的重写应返回实现指定模式的对象。 如果控件没有模式的自定义实现，则可以调用 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 的基类型实现来检索其实现，如果此控件类型不支持模式，则为 null。 例如，可以将自定义 NumericUpDown 控件设置为一个范围内的值，因此，其 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 对等端将实现 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 接口。 下面的示例演示如何重写对等方的 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 方法以响应 <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> 值。  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 方法还可以将子元素指定为模式提供程序。 下面的代码演示 <xref:System.Windows.Controls.ItemsControl> 如何将滚动模式处理传输到其内部 <xref:System.Windows.Controls.ScrollViewer> 控件的对等方。  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 若要为模式处理指定子元素，此代码将获取子元素对象，使用 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> 方法创建对等方，将新对等方的 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 属性设置为当前对等，并返回新的对等。 在子元素上设置 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 会阻止子元素出现在自动化对等树中，并将子元素引发的所有事件指定为源自 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>中指定的控件。 该 <xref:System.Windows.Controls.ScrollViewer> 控件不会出现在自动化树中，并且该控件生成的滚动事件似乎来自 <xref:System.Windows.Controls.ItemsControl> 对象。  
  
### <a name="override-core-methods"></a>"Core" 메서드 재정의  
 자동화 코드는 피어 클래스의 public 메서드를 호출하여 컨트롤에 대한 정보를 가져옵니다. 컨트롤에 대한 정보를 제공하려면 컨트롤 구현이 기본 자동화 피어 클래스에서 제공하는 구현과 다른 경우 이름이 "Core"로 끝나는 각 메서드를 재정의합니다. 控件至少必须实现 <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> 和 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 方法，如以下示例中所示。  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 的实现通过返回 <xref:System.Windows.Automation.ControlType> 值来描述控件。 尽管可以返回 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>，但如果它准确描述了控件，则应返回更具体的控件类型之一。 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> 的返回值需要额外的工作，以便提供程序实现 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]，[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 客户端产品无法预测控制结构、键盘交互和可能的控件模式。  
  
 实现 <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> 和 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 方法，以指示控件是包含数据内容还是在用户界面（或两者）中实现交互角色。 기본적으로 두 메서드 모두 `true`를 반환합니다. 이러한 설정에서는 화면 읽기 프로그램과 같은 자동화 도구의 유용성이 향상되며, 이러한 메서드를 사용하여 자동화 트리를 필터링할 수 있습니다. 如果 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 方法将模式处理传输到子元素对等方，子元素对等方的 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 方法可能会返回 false，以隐藏自动化树中的子元素对等节点。 例如，在 <xref:System.Windows.Controls.ListBox> 中滚动会由 <xref:System.Windows.Controls.ScrollViewer>来处理，而 <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> 的自动化对等方由与 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 关联的 <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>的 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 方法返回。因此，<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 的 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 方法返回 `false`，以便 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 不会出现在自动化树中。  
  
 자동화 피어는 컨트롤에 적절한 기본값을 제공해야 합니다. 请注意，引用控件的 XAML 可以通过包含 <xref:System.Windows.Automation.AutomationProperties> 特性来重写核心方法的对等实现。 예를 들어 다음 XAML에서는 사용자 지정된 두 가지 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 속성이 있는 단추를 만듭니다.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>패턴 공급자 구현  
 如果所属元素直接从 <xref:System.Windows.Controls.Control>派生，则由自定义提供程序实现的接口是显式声明的。 例如，以下代码将为实现范围值的 <xref:System.Windows.Controls.Control> 声明对等方。  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 如果所属控件派生自特定类型的控件（如 <xref:System.Windows.Controls.Primitives.RangeBase>），则对等方可以从等效的派生对等类派生。 在这种情况下，对等方将派生自 <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>，后者提供 <xref:System.Windows.Automation.Provider.IRangeValueProvider>的基实现。 다음 코드에서는 이러한 피어의 선언을 보여 줍니다.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
有关示例实现，请参见[C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)或[Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)实现和使用 NumericUpDown 自定义控件的源代码。  
  
### <a name="raise-events"></a>이벤트 발생  
 자동화 클라이언트는 자동화 이벤트를 구독할 수 있습니다. 自定义控件必须通过调用 <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> 方法报告对控件状态的更改。 同样，在属性值更改时，调用 <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> 方法。 다음 코드에서는 컨트롤 코드 내에서 피어 개체를 가져오고 메서드를 호출하여 이벤트를 발생시키는 방법을 보여 줍니다. 최적화 방법으로 코드는 이 이벤트 유형에 대한 수신기가 있는지 확인합니다. 수신기가 있는 경우에만 이벤트가 발생되면 불필요한 오버헤드를 방지하고 컨트롤이 응답 가능한 상태를 유지하는 데 도움이 됩니다.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>另请参阅

- [UI 자동화 개요](../../ui-automation/ui-automation-overview.md)
- [서버 쪽 UI 자동화 공급자 구현](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [GitHub 上的 NumericUpDownC#自定义控件（）](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [GitHub 上的 NumericUpDown 自定义控件（Visual Basic）](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
