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
ms.openlocfilehash: 00ee19f343d8f471d84f3dc8180e61b7354e3985
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738597"
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="0bb53-102">如何：在 Windows 应用程序中提供帮助</span><span class="sxs-lookup"><span data-stu-id="0bb53-102">How to: Provide Help in a Windows Application</span></span>
<span data-ttu-id="0bb53-103">可以使用的<xref:System.Windows.Forms.HelpProvider>组件将附加到 Windows 窗体上的特定控件的帮助文件中的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0bb53-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="0bb53-104">帮助文件可以是 HTML、HTMLHelp 1.x 或更高版本的格式。</span><span class="sxs-lookup"><span data-stu-id="0bb53-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bb53-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="0bb53-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0bb53-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="0bb53-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0bb53-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="0bb53-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-provide-help"></a><span data-ttu-id="0bb53-108">提供帮助</span><span class="sxs-lookup"><span data-stu-id="0bb53-108">To provide Help</span></span>  
  
1.  <span data-ttu-id="0bb53-109">从**工具箱**，拖动<xref:System.Windows.Forms.HelpProvider>向窗体组件。</span><span class="sxs-lookup"><span data-stu-id="0bb53-109">From the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>  
  
     <span data-ttu-id="0bb53-110">该组件将位于 Windows 窗体设计器底部的栏中。</span><span class="sxs-lookup"><span data-stu-id="0bb53-110">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="0bb53-111">在中**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性设置为.chm、.col 或.htm 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="0bb53-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>  
  
3.  <span data-ttu-id="0bb53-112">选择你在窗体中，然后在另一个控件**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0bb53-112">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>  
  
     <span data-ttu-id="0bb53-113">这是通过传递的字符串<xref:System.Windows.Forms.HelpProvider>组件到帮助文件用于请求相应的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0bb53-113">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>  
  
4.  <span data-ttu-id="0bb53-114">在中**属性**窗口中，将<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>属性的值的<xref:System.Windows.Forms.HelpNavigator>枚举。</span><span class="sxs-lookup"><span data-stu-id="0bb53-114">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>  
  
     <span data-ttu-id="0bb53-115">这可确定以何种方式将 **HelpKeyword** 属性传递给帮助系统。</span><span class="sxs-lookup"><span data-stu-id="0bb53-115">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="0bb53-116">下表显示可能的设置及其说明。</span><span class="sxs-lookup"><span data-stu-id="0bb53-116">The following table shows the possible settings and their descriptions.</span></span>  
  
    |<span data-ttu-id="0bb53-117">成员名称</span><span class="sxs-lookup"><span data-stu-id="0bb53-117">Member Name</span></span>|<span data-ttu-id="0bb53-118">描述</span><span class="sxs-lookup"><span data-stu-id="0bb53-118">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="0bb53-119">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="0bb53-119">AssociateIndex</span></span>|<span data-ttu-id="0bb53-120">指定在指定 URL 中执行指定主题的索引。</span><span class="sxs-lookup"><span data-stu-id="0bb53-120">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|  
    |<span data-ttu-id="0bb53-121">查找</span><span class="sxs-lookup"><span data-stu-id="0bb53-121">Find</span></span>|<span data-ttu-id="0bb53-122">指定显示指定 URL 的搜索页。</span><span class="sxs-lookup"><span data-stu-id="0bb53-122">Specifies that the search page of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="0bb53-123">索引</span><span class="sxs-lookup"><span data-stu-id="0bb53-123">Index</span></span>|<span data-ttu-id="0bb53-124">指定显示指定 URL 的索引。</span><span class="sxs-lookup"><span data-stu-id="0bb53-124">Specifies that the index of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="0bb53-125">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="0bb53-125">KeywordIndex</span></span>|<span data-ttu-id="0bb53-126">指定要搜索的关键字和要在指定 URL 中采取的操作。</span><span class="sxs-lookup"><span data-stu-id="0bb53-126">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|  
    |<span data-ttu-id="0bb53-127">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="0bb53-127">TableOfContents</span></span>|<span data-ttu-id="0bb53-128">指定显示 HTML 1.0 帮助文件的目录。</span><span class="sxs-lookup"><span data-stu-id="0bb53-128">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|  
    |<span data-ttu-id="0bb53-129">主题</span><span class="sxs-lookup"><span data-stu-id="0bb53-129">Topic</span></span>|<span data-ttu-id="0bb53-130">指定显示指定 URL 引用的主题。</span><span class="sxs-lookup"><span data-stu-id="0bb53-130">Specifies that the topic referenced by the specified URL is displayed.</span></span>|  
  
 <span data-ttu-id="0bb53-131">在运行时，按 f1 键时控件 — 对于您设置**HelpKeyword**并**HelpNavigator**属性 — 具有焦点将打开与该关联的帮助文件<xref:System.Windows.Forms.HelpProvider>组件。</span><span class="sxs-lookup"><span data-stu-id="0bb53-131">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>  
  
 <span data-ttu-id="0bb53-132">目前， **HelpNamespace**属性支持以下三种格式的帮助文件：HTMLHelp 1.x、 HTMLHelp 2.0 中和 HTML。</span><span class="sxs-lookup"><span data-stu-id="0bb53-132">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="0bb53-133">因此，可以将 **HelpNamespace** 属性设置为 http:// 地址（如网页）。</span><span class="sxs-lookup"><span data-stu-id="0bb53-133">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="0bb53-134">如果此操作已完成，系统会打开默认浏览器，并显示作为定位标记的 **HelpKeyword** 属性中指定的字符串所对应的网页。</span><span class="sxs-lookup"><span data-stu-id="0bb53-134">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="0bb53-135">定位标记用于跳转到 HTML 页的特定部分。</span><span class="sxs-lookup"><span data-stu-id="0bb53-135">The anchor is used to jump to a specific part of an HTML page.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0bb53-136">一定要先仔细检查从客户端发来的所有信息，再在应用程序中使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="0bb53-136">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="0bb53-137">恶意用户可能会尝试发送或注入可执行脚本、SQL 语句或其他代码。</span><span class="sxs-lookup"><span data-stu-id="0bb53-137">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="0bb53-138">显示用户的输入、将其存储在数据库中或使用它之前，请确定它没有包含可能的不安全信息。</span><span class="sxs-lookup"><span data-stu-id="0bb53-138">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="0bb53-139">通常的检查方法是在收到某个用户发来的输入后，使用正则表达式查找关键字，如“SCRIPT”。</span><span class="sxs-lookup"><span data-stu-id="0bb53-139">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>  
  
 <span data-ttu-id="0bb53-140">此外可以使用<xref:System.Windows.Forms.HelpProvider>组件显示弹出帮助，即使将其配置为显示 Windows 窗体上控件的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="0bb53-140">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="0bb53-141">有关详细信息，请参阅[如何：显示弹出帮助](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb53-141">For more information, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb53-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb53-142">See also</span></span>
- [<span data-ttu-id="0bb53-143">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="0bb53-143">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)
- [<span data-ttu-id="0bb53-144">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="0bb53-144">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)
- [<span data-ttu-id="0bb53-145">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="0bb53-145">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="0bb53-146">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="0bb53-146">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
