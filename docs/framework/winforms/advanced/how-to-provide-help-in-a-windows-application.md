---
title: 如何：在 Windows 应用程序中提供帮助
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 3df8f6eaee72ebdd6cbd03d0bdfde5a7d2270129
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-provide-help-in-a-windows-application"></a>如何：在 Windows 应用程序中提供帮助
你可以使用<xref:System.Windows.Forms.HelpProvider>组件要附加到 Windows 窗体上的特定控件的帮助文件中的帮助主题。 帮助文件可以是 HTML、HTMLHelp 1.x 或更高版本的格式。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-provide-help"></a>提供帮助  
  
1.  从**工具箱**，拖动<xref:System.Windows.Forms.HelpProvider>组件向窗体。  
  
     该组件将位于 Windows 窗体设计器底部的栏中。  
  
2.  在**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.chm、.col 或.htm 帮助文件的属性。  
  
3.  选择另一个控件对窗体中，然后在**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>属性。  
  
     这是通过传递的字符串<xref:System.Windows.Forms.HelpProvider>组件与你的帮助文件，来调用相应的帮助主题。  
  
4.  在**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>属性的值的<xref:System.Windows.Forms.HelpNavigator>枚举。  
  
     这可确定以何种方式将 **HelpKeyword** 属性传递给帮助系统。 下表显示可能的设置及其说明。  
  
    |成员名称|描述|  
    |-----------------|-----------------|  
    |AssociateIndex|指定在指定 URL 中执行指定主题的索引。|  
    |查找|指定显示指定 URL 的搜索页。|  
    |索引|指定显示指定 URL 的索引。|  
    |KeywordIndex|指定要搜索的关键字和要在指定 URL 中采取的操作。|  
    |TableOfContents|指定显示 HTML 1.0 帮助文件的目录。|  
    |主题|指定显示指定 URL 引用的主题。|  
  
 在运行时，按 F1 时控件-为你设置**HelpKeyword**和**HelpNavigator**属性-具有焦点将打开与该关联的帮助文件<xref:System.Windows.Forms.HelpProvider>组件。  
  
 目前，**HelpNamespace** 属性支持下列三种格式的帮助文件：HTMLHelp 1.x、HTMLHelp 2.0 和 HTML。 因此，可以将 **HelpNamespace** 属性设置为 http:// 地址（如网页）。 如果此操作已完成，系统会打开默认浏览器，并显示作为定位标记的 **HelpKeyword** 属性中指定的字符串所对应的网页。 定位标记用于跳转到 HTML 页的特定部分。  
  
> [!IMPORTANT]
>  一定要先仔细检查从客户端发来的所有信息，再在应用程序中使用这些信息。 恶意用户可能会尝试发送或注入可执行脚本、SQL 语句或其他代码。 显示用户的输入、将其存储在数据库中或使用它之前，请确定它没有包含可能的不安全信息。 通常的检查方法是在收到某个用户发来的输入后，使用正则表达式查找关键字，如“SCRIPT”。  
  
 你还可以使用<xref:System.Windows.Forms.HelpProvider>组件以显示弹出帮助，即使你具有配置为显示 Windows 窗体上控件的帮助文件。 有关详细信息，请参阅[如何：显示弹出帮助](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何：显示弹出帮助](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [使用工具提示的控件帮助](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [在 Windows 窗体中集成用户帮助](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows 窗体](../../../../docs/framework/winforms/index.md)
