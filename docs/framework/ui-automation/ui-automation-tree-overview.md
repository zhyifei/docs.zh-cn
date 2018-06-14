---
title: UI 自动化树概述
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0823a569b19d46f32c1cb780470a935f20429c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409118"
---
# <a name="ui-automation-tree-overview"></a>UI 自动化树概述
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 辅助技术产品和测试脚本，用于定位[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树来收集有关的信息[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]及其元素。  
  
 在[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]存在树是根元素 (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>)，表示当前桌面和元素的子元素表示应用程序窗口。 每个这些子元素可以包含元素表示的部分[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]例如菜单、 按钮、 工具栏和列表框。 这些子元素又可以包含列表项之类的元素。  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树不固定的结构，因此很少全部显示其全部显示出来由于它可能包含数千个元素。 可以根据需要生成树的某些部分，添加、移动或删除元素时，树也会发生相应更改。  
  
 UI 自动化提供程序支持[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]通过实现片段中，其中包含根 （通常承载在窗口中） 和一个子树中各项之间的导航树。 但是，提供程序并不参与控件之间的导航。 这由[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]核心借助于默认窗口提供程序中的信息。  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>自动化树的视图  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树可以进行筛选，可以创建视图，仅包含那些<xref:System.Windows.Automation.AutomationElement>特定客户端相关的对象。 此方法允许客户端自定义通过表示的结构[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]到各自的具体需求。  
  
 客户端可以通过以下两种方法来自定义视图：设置范围和筛选。 设置范围是指从基元素开始定义视图的范围，例如，应用程序可能希望仅查找桌面的直接子级，或者查找某个应用程序窗口的所有后代。 筛选是指定义要包括在视图中的元素类型。  
  
 UI 自动化提供程序支持通过定义元素，其中包括属性筛选<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>和<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>属性。  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 提供三个默认视图。 这些视图由所执行筛选的类型定义；任何视图的范围都是由应用程序定义的。 另外，应用程序可以向属性应用其他筛选器，例如，在控件视图中仅包含已启用的控件。  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>原始视图  
 原始视图[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]目录树是完整树的<xref:System.Windows.Automation.AutomationElement>对象的桌面根。 原始视图完全遵循应用程序的本机编程结构，因此是最详细的可用视图。 原始视图还是其他树视图的生成基础。 因为此视图依赖于基础[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]framework、 的原始视图[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]按钮都将具有不同的原始视图比[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]按钮。  
  
 原始视图获取通过搜索元素，而无需指定属性或通过使用<xref:System.Windows.Automation.TreeWalker.RawViewWalker>树中导航。  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>控件视图  
 控件视图[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树简化了辅助技术产品的任务描述[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]因为它紧密映射到最终用户与应用程序交互向最终用户和帮助[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]结构任何可察觉的最终用户。  
  
 控件视图是原始视图的子集。 它包括所有[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]项从最终用户理解为交互式的或相关中的控件的逻辑结构的原始视图[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]。 示例[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]贡献的逻辑结构的项[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]，但并不是交互式本身，列表视图标题、 工具栏、 菜单和状态栏等项容器。 仅针对布局或修饰目的而使用的非交互式项将不会显示在控件视图中。 仅为了将控件放置在对话框中而本身不包含任何信息的面板就是这样的项。 对话框中包含信息和静态文本的图形是在控件视图中显示的非交互式项。 控件视图中包括的非交互式项不能接收键盘焦点。  
  
 控件视图获取通过搜索的元素<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>属性设置为`true`，或通过使用<xref:System.Windows.Automation.TreeWalker.ControlViewWalker>树中导航。  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>内容视图  
 内容视图[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树是控件视图的子集。 它包含[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]中传达真正信息在用户界面中的项包括[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]项可以接收键盘焦点和一些不在一个标签的文本[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]项。 例如，下拉组合框中的值将出现在内容视图中，因为它们表示正由最终用户使用的信息。 在内容视图中，组合框和列表框均表示为一套[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]其中可以选择一个，或可能是多个项的项。 由于内容视图旨在显示要呈现给用户的数据或内容，因此，内容视图中不存在如下情况：始终有一项处于打开状态，而另有一项是可以展开和折叠的。  
  
 内容视图获取通过搜索的元素<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>属性设置为`true`，或通过使用<xref:System.Windows.Automation.TreeWalker.ContentViewWalker>树中导航。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Automation.AutomationElement>  
 [UI 自动化概述](../../../docs/framework/ui-automation/ui-automation-overview.md)
