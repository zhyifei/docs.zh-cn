---
title: WPF 自定义控件的 UI 自动化
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
ms.openlocfilehash: fbd19591c260b0ad160339b45fd762e7a87bbc74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>WPF 自定义控件的 UI 自动化
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] 提供了一个通用接口，自动化客户端可使用该接口来检查或操作各种平台和框架的用户界面。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 使质量保证（测试）代码和具有辅助功能的应用程序（如屏幕阅读器）能够检查用户界面元素，以及能够模拟与其他代码中的用户元素进行的用户交互。 有关跨所有平台的 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 的信息，请参阅“辅助功能”。  
  
 本主题介绍如何实现在 WPF 应用程序中运行的自定义控件的服务器端 UI 自动化提供程序。 WPF 通过等同于用户界面元素树的对等自动化对象树来支持 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]。 测试代码和提供辅助功能的应用程序可以直接使用自动化对等对象（适用于进程内代码），也可以通过 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 提供的通用接口使用自动化对等对象。  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>自动化对等类  
 WPF 控件支持[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]访问对等类派生自的树<xref:System.Windows.Automation.Peers.AutomationPeer>。 按照约定，对等类名以控件类名开头，以“AutomationPeer”结尾。 例如，<xref:System.Windows.Automation.Peers.ButtonAutomationPeer>是适用于的对等<xref:System.Windows.Controls.Button>控件类。 对等类大致相当于 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 控件类型，但特定于 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 元素。 通过 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 接口访问 WPF 应用程序的自动化代码不直接使用自动化对等，但同一进程空间中的自动化代码可以直接使用自动化对等。  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>内置的自动化对等类  
 如果元素接受用户的接口活动，或者如果元素包含屏幕阅读器应用程序的用户所需的信息，则这些元素会实现一个自动化对等类。 并非所有 WPF 视觉元素都具有自动化对等。 实现自动化对等节点的类的示例包括<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.TextBox>，和<xref:System.Windows.Controls.Label>。 未实现自动化对等节点的类的示例是派生自的类<xref:System.Windows.Controls.Decorator>，如<xref:System.Windows.Controls.Border>，基于和类<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Controls.Canvas>。  
  
 基<xref:System.Windows.Controls.Control>类没有相应的对等类。 如果你需要一个对等类对应于自定义控件派生自<xref:System.Windows.Controls.Control>，应派生自定义对等类从<xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>。  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>派生对等的安全注意事项  
 自动化对等必须在部分信任环境中运行。 UIAutomationClient 程序集中的代码未配置为在部分信任环境中运行，自动化对等代码不应引用该程序集。 应改用 UIAutomationTypes 程序集中的类。 例如，你应使用<xref:System.Windows.Automation.AutomationElementIdentifiers>UIAutomationTypes 程序集，它对应于类<xref:System.Windows.Automation.AutomationElement>UIAutomationClient 程序集中的类。 可以安全地在自动化对等代码中引用 UIAutomationTypes 程序集。  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>对等导航  
 找到的自动化对等方之后, 在过程代码可以在树中导航对等方通过调用对象的<xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A>和<xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A>方法。 各之间的导航[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]控件内的元素支持对等节点的实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A>方法。 UI 自动化系统调用此方法生成控件内包含的子元素树（例如，列表框中的列表项）。 默认值<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType>方法遍历要生成自动化对等节点的树的元素的可视化树。 自定义控件重写此方法以向自动化客户端公开子元素，这会返回传达信息或允许用户交互的元素自动化对等。  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>派生对等中的自定义项  
 派生自的所有类<xref:System.Windows.UIElement>和<xref:System.Windows.ContentElement>包含受保护的虚拟方法<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>。 WPF 调用<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>获取每个控件的自动化对等对象。 自动化代码可使用对等来获取有关控件特征和功能的信息，并模拟交互使用。 支持自动化的自定义控件必须重写<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>返回派生自的类的实例和<xref:System.Windows.Automation.Peers.AutomationPeer>。 例如，如果自定义控件派生自<xref:System.Windows.Controls.Primitives.ButtonBase>类，则返回的对象<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>应派生自<xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>。  
  
 实现自定义控件时，必须重写自动化对等基类中的“Core”方法，这些方法描述了特定于自定义控件的唯一行为。  
  
### <a name="override-oncreateautomationpeer"></a>重写 OnCreateAutomationPeer  
 重写<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>方法为您的自定义控件，以便它返回你的提供程序对象，必须直接或间接派生自<xref:System.Windows.Automation.Peers.AutomationPeer>。  
  
### <a name="override-getpattern"></a>重写 GetPattern  
 自动化对等简化了服务器端 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 提供程序的一部分实现，但自定义控件自动化对等仍必须处理模式接口。 非 WPF 提供程序，如对等节点支持控件模式通过提供中接口的实现<xref:System.Windows.Automation.Provider?displayProperty=nameWithType>命名空间，如<xref:System.Windows.Automation.Provider.IInvokeProvider>。 控件模式接口可以由对等本身或其他对象实现。 对等节点的实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>返回支持指定的模式的对象。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 代码调用<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>方法并指定<xref:System.Windows.Automation.Peers.PatternInterface>枚举值。 重写<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>应返回实现指定的模式的对象。 如果控件不具有一种模式的自定义实现，则可调用基类型实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>检索其实现或 null，如果模式不支持此控件类型。 例如，自定义的 NumericUpDown 控件可以设置为范围内的值以便其[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]对等方将实现<xref:System.Windows.Automation.Provider.IRangeValueProvider>接口。 下面的示例演示如何对等节点的<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>重写方法以响应<xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType>值。  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 A<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>方法还可以指定子元素模式提供程序。 下面的代码演示如何<xref:System.Windows.Controls.ItemsControl>将 scroll 模式处理到其内部的对等方<xref:System.Windows.Controls.ScrollViewer>控件。  
  
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
  
 若要指定的模式处理的子元素，此代码将获取子元素的对象，通过使用创建对等方<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>方法，设置<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>到当前对等方，新的对等方属性并返回新的对等方。 设置<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>子元素可防止子元素出现在自动化对等树中并将引发的子元素的所有事件都指定为源自中指定的控件<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>。 <xref:System.Windows.Controls.ScrollViewer>控件未出现在自动化树中，和它所生成的滚动事件显示为来自<xref:System.Windows.Controls.ItemsControl>对象。  
  
### <a name="override-core-methods"></a>重写“Core”方法  
 自动化代码通过调用对等类的公共方法来获取控件的相关信息。 在控件实现不同于自动化对等基类提供的实现的情况下，若要提供控件的相关信息，请重写名称以“Core”结尾的每个方法。 你的控件必须实现至少<xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A>和<xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>方法，如下面的示例中所示。  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>通过返回描述您的控件<xref:System.Windows.Automation.ControlType>值。 尽管您可以返回<xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>，如果它准确地描述您的控件应返回更具体的控件类型之一。 返回值<xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>需要额外的工作，以便该提供程序实现[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]，和[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]客户端产品不能以应对预期的控件结构、 键盘交互和可能的控件模式。  
  
 实现<xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A>和<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>方法以指示控件是否包含数据内容或满足的交互式角色中的用户界面 （或两者）。 默认情况下，这两个方法返回 `true`。 这些设置提高了屏幕阅读器等自动化工具的可用性，此类工具可使用这些方法筛选自动化树。 如果你<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>方法传输模式处理到一个子元素对等子元素对等的<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>方法可以返回为 false，则隐藏在自动化树中的子元素对等方。 例如，在滚动<xref:System.Windows.Controls.ListBox>由处理<xref:System.Windows.Controls.ScrollViewer>，和自动化对等方<xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType>返回<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>方法<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>关联<xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>。因此，<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>方法<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>返回`false`，以便<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>在自动化树中不显示。  
  
 自动化对等应为控件提供合适的默认值。 请注意，引用您的控件的 XAML 可以通过重写的核心方法对等实现包括<xref:System.Windows.Automation.AutomationProperties>属性。 例如，以下 XAML 创建的按钮具有两个自定义的 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 属性。  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>实现模式提供程序  
 如果直接从所属的元素派生自定义提供程序实现的接口都显式声明<xref:System.Windows.Controls.Control>。 例如，下面的代码声明的对等方<xref:System.Windows.Controls.Control>实现范围值。  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 如果所属的控件如派生于特定类型的控件<xref:System.Windows.Controls.Primitives.RangeBase>，对等方可以派生自等效派生的对等类。 在这种情况下，对等方将派生自<xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>，其中提供的基实现<xref:System.Windows.Automation.Provider.IRangeValueProvider>。 以下代码演示了此类对等的声明。  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 有关示例实现，请参阅[带有主题和 UI 自动化支持示例的 NumericUpDown 自定义控件](http://go.microsoft.com/fwlink/?LinkID=160025)。  
  
### <a name="raise-events"></a>引发事件  
 自动化客户端可订阅自动化事件。 自定义控件必须报告来控制通过调用状态的更改<xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>方法。 同样，当属性值更改，则调用<xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>方法。 以下代码演示了如何在控件代码内获取对等对象，并调用一个方法来引发事件。 作为一种优化，该代码会确定是否有适用于此事件类型的任何侦听器。 仅当有侦听器时才引发事件，可避免不必要的开销，有助于控件保持响应状态。  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>请参阅  
 [UI 自动化概述](../../../../docs/framework/ui-automation/ui-automation-overview.md)  
 [主题和 UI 自动化支持示例的 NumericUpDown 自定义控件](http://go.microsoft.com/fwlink/?LinkID=160025)  
 [服务器端 UI 自动化提供程序实现](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
