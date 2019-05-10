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
ms.openlocfilehash: 19bf6a8de3f9ddd5babd149747df87c54b456aeb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211366"
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="b47da-102">如何：在 Windows 应用程序中提供帮助</span><span class="sxs-lookup"><span data-stu-id="b47da-102">How to: Provide Help in a Windows Application</span></span>

<span data-ttu-id="b47da-103">可以使用的<xref:System.Windows.Forms.HelpProvider>组件将附加到 Windows 窗体上的特定控件的帮助文件中的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b47da-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="b47da-104">帮助文件可以是 HTML、HTMLHelp 1.x 或更高版本的格式。</span><span class="sxs-lookup"><span data-stu-id="b47da-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>

## <a name="provide-help"></a><span data-ttu-id="b47da-105">提供的帮助信息</span><span class="sxs-lookup"><span data-stu-id="b47da-105">Provide Help</span></span>

1. <span data-ttu-id="b47da-106">在 Visual Studio 中，从**工具箱**，拖动<xref:System.Windows.Forms.HelpProvider>向窗体组件。</span><span class="sxs-lookup"><span data-stu-id="b47da-106">In Visual Studio, from the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>

     <span data-ttu-id="b47da-107">该组件将位于 Windows 窗体设计器底部的栏中。</span><span class="sxs-lookup"><span data-stu-id="b47da-107">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b47da-108">在中**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性设置为.chm、.col 或.htm 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="b47da-108">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>

3. <span data-ttu-id="b47da-109">选择你在窗体中，然后在另一个控件**属性**窗口中，设置<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b47da-109">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>

     <span data-ttu-id="b47da-110">这是通过传递的字符串<xref:System.Windows.Forms.HelpProvider>组件到帮助文件用于请求相应的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b47da-110">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>

4. <span data-ttu-id="b47da-111">在中**属性**窗口中，将<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>属性的值的<xref:System.Windows.Forms.HelpNavigator>枚举。</span><span class="sxs-lookup"><span data-stu-id="b47da-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>

     <span data-ttu-id="b47da-112">这可确定以何种方式将 **HelpKeyword** 属性传递给帮助系统。</span><span class="sxs-lookup"><span data-stu-id="b47da-112">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="b47da-113">下表显示可能的设置及其说明。</span><span class="sxs-lookup"><span data-stu-id="b47da-113">The following table shows the possible settings and their descriptions.</span></span>

    |<span data-ttu-id="b47da-114">成员名称</span><span class="sxs-lookup"><span data-stu-id="b47da-114">Member Name</span></span>|<span data-ttu-id="b47da-115">描述</span><span class="sxs-lookup"><span data-stu-id="b47da-115">Description</span></span>|
    |-----------------|-----------------|
    |<span data-ttu-id="b47da-116">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="b47da-116">AssociateIndex</span></span>|<span data-ttu-id="b47da-117">指定在指定 URL 中执行指定主题的索引。</span><span class="sxs-lookup"><span data-stu-id="b47da-117">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|
    |<span data-ttu-id="b47da-118">查找</span><span class="sxs-lookup"><span data-stu-id="b47da-118">Find</span></span>|<span data-ttu-id="b47da-119">指定显示指定 URL 的搜索页。</span><span class="sxs-lookup"><span data-stu-id="b47da-119">Specifies that the search page of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="b47da-120">索引</span><span class="sxs-lookup"><span data-stu-id="b47da-120">Index</span></span>|<span data-ttu-id="b47da-121">指定显示指定 URL 的索引。</span><span class="sxs-lookup"><span data-stu-id="b47da-121">Specifies that the index of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="b47da-122">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="b47da-122">KeywordIndex</span></span>|<span data-ttu-id="b47da-123">指定要搜索的关键字和要在指定 URL 中采取的操作。</span><span class="sxs-lookup"><span data-stu-id="b47da-123">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|
    |<span data-ttu-id="b47da-124">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="b47da-124">TableOfContents</span></span>|<span data-ttu-id="b47da-125">指定显示 HTML 1.0 帮助文件的目录。</span><span class="sxs-lookup"><span data-stu-id="b47da-125">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|
    |<span data-ttu-id="b47da-126">主题</span><span class="sxs-lookup"><span data-stu-id="b47da-126">Topic</span></span>|<span data-ttu-id="b47da-127">指定显示指定 URL 引用的主题。</span><span class="sxs-lookup"><span data-stu-id="b47da-127">Specifies that the topic referenced by the specified URL is displayed.</span></span>|

 <span data-ttu-id="b47da-128">在运行时，按 f1 键时控件 — 对于您设置**HelpKeyword**并**HelpNavigator**属性 — 具有焦点将打开与该关联的帮助文件<xref:System.Windows.Forms.HelpProvider>组件。</span><span class="sxs-lookup"><span data-stu-id="b47da-128">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>

 <span data-ttu-id="b47da-129">目前， **HelpNamespace**属性支持以下三种格式的帮助文件：HTMLHelp 1.x、 HTMLHelp 2.0 中和 HTML。</span><span class="sxs-lookup"><span data-stu-id="b47da-129">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="b47da-130">因此，可以将 **HelpNamespace** 属性设置为 http:// 地址（如网页）。</span><span class="sxs-lookup"><span data-stu-id="b47da-130">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="b47da-131">如果此操作已完成，系统会打开默认浏览器，并显示作为定位标记的 **HelpKeyword** 属性中指定的字符串所对应的网页。</span><span class="sxs-lookup"><span data-stu-id="b47da-131">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="b47da-132">定位标记用于跳转到 HTML 页的特定部分。</span><span class="sxs-lookup"><span data-stu-id="b47da-132">The anchor is used to jump to a specific part of an HTML page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b47da-133">一定要先仔细检查从客户端发来的所有信息，再在应用程序中使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="b47da-133">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="b47da-134">恶意用户可能会尝试发送或注入可执行脚本、SQL 语句或其他代码。</span><span class="sxs-lookup"><span data-stu-id="b47da-134">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="b47da-135">显示用户的输入、将其存储在数据库中或使用它之前，请确定它没有包含可能的不安全信息。</span><span class="sxs-lookup"><span data-stu-id="b47da-135">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="b47da-136">通常的检查方法是在收到某个用户发来的输入后，使用正则表达式查找关键字，如“SCRIPT”。</span><span class="sxs-lookup"><span data-stu-id="b47da-136">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>

<span data-ttu-id="b47da-137">此外可以使用<xref:System.Windows.Forms.HelpProvider>组件显示弹出帮助，即使将其配置为显示 Windows 窗体上控件的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="b47da-137">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="b47da-138">有关详细信息，请参阅[如何：显示弹出帮助](how-to-display-pop-up-help.md)。</span><span class="sxs-lookup"><span data-stu-id="b47da-138">For more information, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b47da-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b47da-139">See also</span></span>

- [<span data-ttu-id="b47da-140">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="b47da-140">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)
- [<span data-ttu-id="b47da-141">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="b47da-141">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="b47da-142">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="b47da-142">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="b47da-143">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b47da-143">Windows Forms</span></span>](../index.md)
