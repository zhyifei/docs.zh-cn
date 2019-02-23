---
title: Windows 窗体控件和等效的 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: e98a850e6846c73c4df698e2a5414481611bb63d
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748565"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="6f803-102">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6f803-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="6f803-103">许多[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件都有等效[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件，但一些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件中有没有等效项[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f803-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="6f803-104">本主题将比较这两种技术所提供的控件类型。</span><span class="sxs-lookup"><span data-stu-id="6f803-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="6f803-105">您始终可以使用互操作来承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中没有等效项的控件在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f803-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="6f803-106">下表显示了哪些[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件和组件都有等效项[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控制功能。</span><span class="sxs-lookup"><span data-stu-id="6f803-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="6f803-107">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="6f803-107">Windows Forms control</span></span>|<span data-ttu-id="6f803-108">等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="6f803-108">WPF equivalent control</span></span>|<span data-ttu-id="6f803-109">备注</span><span class="sxs-lookup"><span data-stu-id="6f803-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="6f803-110">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="6f803-111"><xref:System.Windows.Controls.ListBox> 与撰写。</span><span class="sxs-lookup"><span data-stu-id="6f803-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="6f803-112">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="6f803-113"><xref:System.Windows.Controls.ComboBox> 不支持自动完成。</span><span class="sxs-lookup"><span data-stu-id="6f803-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="6f803-114"><xref:System.Windows.Controls.TextBox> 和两个<xref:System.Windows.Controls.Primitives.RepeatButton>控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="6f803-115">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="6f803-116"><xref:System.Windows.Controls.WrapPanel> 或 <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="6f803-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="6f803-117">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="6f803-118">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="6f803-119"><xref:System.Windows.Window> 不支持子窗口。</span><span class="sxs-lookup"><span data-stu-id="6f803-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="6f803-120">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-120">No equivalent control.</span></span>|<span data-ttu-id="6f803-121">没有 F1 帮助。</span><span class="sxs-lookup"><span data-stu-id="6f803-121">No F1 Help.</span></span> <span data-ttu-id="6f803-122">"这是什么"帮助替换为工具提示。</span><span class="sxs-lookup"><span data-stu-id="6f803-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="6f803-123">滚动内置容器控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="6f803-124">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="6f803-125">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-125">No equivalent control.</span></span>|<span data-ttu-id="6f803-126">可以使用<xref:System.Windows.Documents.Hyperlink>承载流内容内的超链接的类。</span><span class="sxs-lookup"><span data-stu-id="6f803-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="6f803-127"><xref:System.Windows.Controls.ListView>控件提供了一个只读的详细信息视图。</span><span class="sxs-lookup"><span data-stu-id="6f803-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="6f803-128">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="6f803-129"><xref:System.Windows.Controls.Menu> 控件样式设置类似的行为和外观<xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="6f803-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="6f803-130">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="6f803-131"><xref:System.Windows.Controls.TextBox> 和两个<xref:System.Windows.Controls.Primitives.RepeatButton>控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="6f803-132"><xref:Microsoft.Win32.OpenFileDialog>类是[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]周围的包装器[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="6f803-133">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="6f803-134">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="6f803-135">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="6f803-136">没有等效的控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="6f803-137"><xref:Microsoft.Win32.SaveFileDialog>类是[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]周围的包装器[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="6f803-138"><xref:System.Windows.Controls.ToolBar> 与撰写。</span><span class="sxs-lookup"><span data-stu-id="6f803-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="6f803-139"><xref:System.Windows.Controls.ToolBar> 与撰写。</span><span class="sxs-lookup"><span data-stu-id="6f803-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="6f803-140"><xref:System.Windows.Controls.ToolBar> 与撰写。</span><span class="sxs-lookup"><span data-stu-id="6f803-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="6f803-141"><xref:System.Windows.Controls.ToolBar> 与撰写。</span><span class="sxs-lookup"><span data-stu-id="6f803-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="6f803-142">滚动内置容器控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="6f803-143"><xref:System.Windows.Controls.Frame>， <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6f803-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="6f803-144"><xref:System.Windows.Controls.Frame>控件可以承载的 HTML 页面。</span><span class="sxs-lookup"><span data-stu-id="6f803-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="6f803-145">在中启动[!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]，则<xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>控件可以承载的 HTML 页面，并且还支持<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="6f803-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f803-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f803-146">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="6f803-147">[WPF 设计器的 Windows 窗体开发人员](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f803-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="6f803-148">演练：承载在 WPF 中的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="6f803-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="6f803-149">演练：承载 WPF 复合控件在 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="6f803-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="6f803-150">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="6f803-150">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
