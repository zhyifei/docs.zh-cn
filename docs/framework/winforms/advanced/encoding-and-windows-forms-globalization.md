---
title: 编码和 Windows 窗体全球化
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: f8e56642b6325454d2d55cd3a3d3a83d201c2eb5
ms.sourcegitcommit: 5e05f983e63d5bbd8c0b246d02c6e4f23d2fc1db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "67151991"
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="b4f93-102">编码和 Windows 窗体全球化</span><span class="sxs-lookup"><span data-stu-id="b4f93-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="b4f93-103">Windows 窗体应用程序完全支持 Unicode，这意味着每个字符都用唯一编号表示，无论何种平台、程序或语音都是如此。</span><span class="sxs-lookup"><span data-stu-id="b4f93-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="b4f93-104">有关 Unicode 的详细信息，请参阅[Unicode 联盟网站](https://www.unicode.org)。</span><span class="sxs-lookup"><span data-stu-id="b4f93-104">For more information about Unicode, see the [Unicode consortium Web site](https://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="b4f93-105">Unicode 的优点</span><span class="sxs-lookup"><span data-stu-id="b4f93-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="b4f93-106">启用 Unicode 的窗体的优点包括，能够处理仅限 Unicode（例如印地语）的脚本。</span><span class="sxs-lookup"><span data-stu-id="b4f93-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="b4f93-107">此外，还可以在单个窗体上使用多种语言。</span><span class="sxs-lookup"><span data-stu-id="b4f93-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="b4f93-108">以 Unicode 格式，所有字符都是两个字节长，所以不需要执行任何特殊操作来表示双字节字符。</span><span class="sxs-lookup"><span data-stu-id="b4f93-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="b4f93-109">还可以编写可在所有平台上工作的单个代码集。</span><span class="sxs-lookup"><span data-stu-id="b4f93-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="b4f93-110">这是从早期版本的 Visual Basic 中，您不得不编写针对不同平台，例如 Windows NT 不同的代码更改和[!INCLUDE[win98](../../../../includes/win98-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b4f93-110">This is a change from previous versions of Visual Basic, in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="b4f93-111">但是，某些控件不支持在 [!INCLUDE[win98](../../../../includes/win98-md.md)] 和 Windows Millennium Edition 中启用 Unicode。</span><span class="sxs-lookup"><span data-stu-id="b4f93-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="b4f93-112">全部继承自公共控件，这些控件将使用处理数据的 Windows 代码页，为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="b4f93-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as ANSI.</span></span> <span data-ttu-id="b4f93-113">这些控件包括：<xref:System.Windows.Forms.TabControl>、<xref:System.Windows.Forms.ListView>、<xref:System.Windows.Forms.TreeView>、<xref:System.Windows.Forms.DateTimePicker>、<xref:System.Windows.Forms.MonthCalendar>、<xref:System.Windows.Forms.TrackBar>、<xref:System.Windows.Forms.ProgressBar>、<xref:System.Windows.Forms.ImageList>、<xref:System.Windows.Forms.ToolBar> 和 <xref:System.Windows.Forms.StatusBar>。</span><span class="sxs-lookup"><span data-stu-id="b4f93-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="b4f93-114">因此，不能在列出的平台上的这些控件中显示 Unicode 数据。</span><span class="sxs-lookup"><span data-stu-id="b4f93-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="b4f93-115">例如，不能在英语版 [!INCLUDE[win98](../../../../includes/win98-md.md)] 操作系统上显示日语字符。</span><span class="sxs-lookup"><span data-stu-id="b4f93-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="b4f93-116">对于 <xref:System.Windows.Forms.ToolBar> 和 <xref:System.Windows.Forms.StatusBar> 控件具有 Unicode 意识的替代项，可使用 <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.StatusStrip> 控件替换这些旧控件。</span><span class="sxs-lookup"><span data-stu-id="b4f93-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="b4f93-117">要想维护应用程序中各可视化元素之间的外观和感觉，可使用用于呈现菜单的 <xref:System.Windows.Forms.MenuStrip> 控件代替 <xref:System.Windows.Forms.MainMenu>。</span><span class="sxs-lookup"><span data-stu-id="b4f93-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="b4f93-118">正如 <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.StatusStrip> 一样，<xref:System.Windows.Forms.MenuStrip> 还可以处理和显示 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="b4f93-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f93-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4f93-119">See also</span></span>

- [<span data-ttu-id="b4f93-120">全球化 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="b4f93-120">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
