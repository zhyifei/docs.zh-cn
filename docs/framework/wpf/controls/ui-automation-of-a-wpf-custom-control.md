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
ms.openlocfilehash: 9c33d0e5da70820041ba2a2881082d9f7d179fc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187498"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>WPF 自定义控件的 UI 自动化
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] 提供了一个通用接口，自动化客户端可使用该接口来检查或操作各种平台和框架的用户界面。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 使质量保证（测试）代码和具有辅助功能的应用程序（如屏幕阅读器）能够检查用户界面元素，以及能够模拟与其他代码中的用户元素进行的用户交互。 有关跨所有平台的 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 的信息，请参阅“辅助功能”。  
  
 本主题介绍如何实现在 WPF 应用程序中运行的自定义控件的服务器端 UI 自动化提供程序。 WPF 通过等同于用户界面元素树的对等自动化对象树来支持 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]。 测试代码和提供辅助功能的应用程序可以直接使用自动化对等对象（适用于进程内代码），也可以通过 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 提供的通用接口使用自动化对等对象。  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>自动化对等类  
 WPF 通过[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]派生自<xref:System.Windows.Automation.Peers.AutomationPeer>的对等类树控制支持。 按照约定，对等类名以控件类名开头，以“AutomationPeer”结尾。 例如，<xref:System.Windows.Automation.Peers.ButtonAutomationPeer>是控件类的<xref:System.Windows.Controls.Button>对等类。 对等类大致等同于[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]控件类型，但特定于 WPF 元素。 通过 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 接口访问 WPF 应用程序的自动化代码不直接使用自动化对等，但同一进程空间中的自动化代码可以直接使用自动化对等。  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>内置的自动化对等类  
 如果元素接受用户的接口活动，或者如果元素包含屏幕阅读器应用程序的用户所需的信息，则这些元素会实现一个自动化对等类。 并非所有 WPF 视觉元素都具有自动化对等。 实现自动化对等体的类示例是<xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox>。<xref:System.Windows.Controls.Label>和 。 不实现自动化对等体的类的示例是从 派生的<xref:System.Windows.Controls.Decorator>类，如<xref:System.Windows.Controls.Border><xref:System.Windows.Controls.Panel><xref:System.Windows.Controls.Grid><xref:System.Windows.Controls.Canvas>  
  
 基<xref:System.Windows.Controls.Control>类没有相应的对等类。 如果需要对等类来对应于派生自<xref:System.Windows.Controls.Control>的自定义控件，则应从<xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>派生自定义对等类。  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>派生对等的安全注意事项  
 自动化对等必须在部分信任环境中运行。 UIAutomationClient 程序集中的代码未配置为在部分信任环境中运行，自动化对等代码不应引用该程序集。 应改用 UIAutomationTypes 程序集中的类。 例如，应使用 UIAutomationType 程序集中的<xref:System.Windows.Automation.AutomationElementIdentifiers>类，该程序集对应于 UIAutomationClient 程序集中的<xref:System.Windows.Automation.AutomationElement>类。 可以安全地在自动化对等代码中引用 UIAutomationTypes 程序集。  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>对等导航  
 找到自动化对等体后，进程内代码可以通过调用对象<xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A>和方法<xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A>来导航对等树。 控件中的 WPF 元素之间的导航由对等体的方法实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A>提供支持。 UI 自动化系统调用此方法生成控件内包含的子元素树（例如，列表框中的列表项）。 默认<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType>方法遍历元素的可视树以生成自动化对等体的树。 自定义控件重写此方法以向自动化客户端公开子元素，这会返回传达信息或允许用户交互的元素自动化对等。  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>派生对等中的自定义项  
 派生自<xref:System.Windows.UIElement>并<xref:System.Windows.ContentElement>包含受保护虚拟方法<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>的所有类。 WPF<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>调用以获取每个控件的自动化对等对象。 自动化代码可使用对等来获取有关控件特征和功能的信息，并模拟交互使用。 支持自动化的自定义控件必须重写<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>并返回派生自<xref:System.Windows.Automation.Peers.AutomationPeer>的类的实例。 例如，如果自定义控件派生自<xref:System.Windows.Controls.Primitives.ButtonBase>类，则返回的对象<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>应派生自<xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>。  
  
 实现自定义控件时，必须重写自动化对等基类中的“Core”方法，这些方法描述了特定于自定义控件的唯一行为。  
  
### <a name="override-oncreateautomationpeer"></a>重写 OnCreateAutomationPeer  
 重写自定义<xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>控件的方法，以便它返回提供程序对象，该对象必须直接或间接派生自<xref:System.Windows.Automation.Peers.AutomationPeer>。  
  
### <a name="override-getpattern"></a>重写 GetPattern  
 自动化对等简化了服务器端 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 提供程序的一部分实现，但自定义控件自动化对等仍必须处理模式接口。 与非 WPF 提供程序一样，对等体通过在<xref:System.Windows.Automation.Provider?displayProperty=nameWithType>命名空间（如<xref:System.Windows.Automation.Provider.IInvokeProvider>中）中提供接口的实现来支持控制模式。 控件模式接口可以由对等本身或其他对象实现。 对等体的实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>返回支持指定模式的对象。 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]代码调用<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>方法并指定<xref:System.Windows.Automation.Peers.PatternInterface>枚举值。 的重写<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>应返回实现指定模式的对象。 如果控件没有模式的自定义实现，则可以调用 基类型的实现<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>来检索其实现，如果此控件类型不支持该模式，则可以调用 其实现。 例如，可以将自定义数字 UpDown 控件设置为范围内的值，因此其[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]对等控件将实现<xref:System.Windows.Automation.Provider.IRangeValueProvider>接口。 下面的示例演示如何重写对等体<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>的方法以响应<xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType>值。  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 方法<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A>还可以将子元素指定为模式提供程序。 以下代码显示如何<xref:System.Windows.Controls.ItemsControl>将滚动模式处理传输到其内部控制<xref:System.Windows.Controls.ScrollViewer>的对等体。  
  
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
  
 要指定模式处理的子元素，此代码获取子元素对象，使用<xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>方法创建对等体，将新对等<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>体的属性设置到当前对等体，并返回新的对等体。 在<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>子元素上设置可防止子元素出现在自动化对等树中，并将子元素引发的所有事件指定为源自 中<xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>指定的控件。 控件<xref:System.Windows.Controls.ScrollViewer>不显示在自动化树中，并且它生成的滚动事件似乎源自对象<xref:System.Windows.Controls.ItemsControl>。  
  
### <a name="override-core-methods"></a>重写“Core”方法  
 自动化代码通过调用对等类的公共方法来获取控件的相关信息。 在控件实现不同于自动化对等基类提供的实现的情况下，若要提供控件的相关信息，请重写名称以“Core”结尾的每个方法。 至少，控件必须实现 和<xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A><xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>方法，如以下示例所示。  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 的<xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>实现通过返回<xref:System.Windows.Automation.ControlType>值来描述控件。 尽管可以返回<xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>，但如果控件准确描述，则应返回其中一种更具体的控件类型。 返回值 需要<xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>提供程序实现的额外工作[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]，并且[!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]客户端产品无法预测控制结构、键盘交互和可能的控制模式。  
  
 实现<xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A>和<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>方法以指示控件是否包含数据内容或是否在用户界面（或两者）中完成交互式角色。 默认情况下，这两个方法返回 `true`。 这些设置提高了屏幕阅读器等自动化工具的可用性，此类工具可使用这些方法筛选自动化树。 如果<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>方法将模式处理传输到子元素对等体，子元素对等体<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>的方法可以返回 false 以从自动化树中隐藏子元素对等体。 例如<xref:System.Windows.Controls.ListBox>，在 中滚动由<xref:System.Windows.Controls.ScrollViewer>处理，并且 的<xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType>自动化对等体由 与<xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A>关联的 方法<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>返回<xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>。因此，<xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>该方法<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>返回`false`，使<xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>不会在自动化树中出现。  
  
 自动化对等应为控件提供合适的默认值。 请注意，引用控件的 XAML 可以通过包括<xref:System.Windows.Automation.AutomationProperties>属性来覆盖核心方法的对等实现。 例如，以下 XAML 创建的按钮具有两个自定义的 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 属性。  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>实现模式提供程序  
 如果拥有元素直接派生自<xref:System.Windows.Controls.Control>，则显式声明由自定义提供程序实现的接口。 例如，以下代码声明实现范围值的 的<xref:System.Windows.Controls.Control>对等方。  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 如果所属控件派生自特定类型的控件（如<xref:System.Windows.Controls.Primitives.RangeBase>，对等体）可以从等效派生的对等类派生。 在这种情况下，对等体将派生自<xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>，后者提供 的基本<xref:System.Windows.Automation.Provider.IRangeValueProvider>实现。 以下代码演示了此类对等的声明。  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
有关实现的示例，请参阅实现和使用数字 UpDown 自定义控件的[C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)或[可视化基本](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)源代码。  
  
### <a name="raise-events"></a>引发事件  
 自动化客户端可订阅自动化事件。 自定义控件必须通过调用<xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>方法报告更改以控制状态。 同样，当属性值发生更改时，调用<xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>方法。 以下代码演示了如何在控件代码内获取对等对象，并调用一个方法来引发事件。 作为一种优化，该代码会确定是否有适用于此事件类型的任何侦听器。 仅当有侦听器时才引发事件，可避免不必要的开销，有助于控件保持响应状态。  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>另请参阅

- [UI 自动化概述](../../ui-automation/ui-automation-overview.md)
- [服务器端 UI 自动化提供程序实现](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [GitHub 上的数字向上自定义控件 （C#）](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [GitHub 上的数字向上自定义控件（可视基本控件）](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
