---
title: 如何：在 Windows 窗体应用程序中响应字体方案更改
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 455609ea602f450803718f5be34618b087560d21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539447"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="9fa0d-102">如何：在 Windows 窗体应用程序中响应字体方案更改</span><span class="sxs-lookup"><span data-stu-id="9fa0d-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="9fa0d-103">在 Windows 操作系统，用户可以更改系统范围的字体设置，以使显示的默认字体放大或缩小。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="9fa0d-104">更改这些字体设置为有视觉障碍并需要更大的类型来读取其屏幕上的文本的用户至关重要。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="9fa0d-105">你可以调整 Windows 窗体应用程序以通过增加或减少的大小的窗体和所有包含的文本的字体方案更改时对这些更改做出响应。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="9fa0d-106">如果你想窗体以动态地适应字体大小的更改，你可以将代码添加到你的窗体。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="9fa0d-107">通常情况下，Windows 窗体使用的默认字体是返回的字体<xref:Microsoft.Win32>命名空间调用`GetStockObject(DEFAULT_GUI_FONT)`。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="9fa0d-108">此调用所返回的字体仅屏幕分辨率更改时进行更改。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="9fa0d-109">下面的过程中所示，你的代码必须更改到的默认字体<xref:System.Drawing.SystemFonts.IconTitleFont%2A>的字体大小的更改进行响应。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="9fa0d-110">若要使用的桌面的字体和响应字体方案更改</span><span class="sxs-lookup"><span data-stu-id="9fa0d-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="9fa0d-111">创建窗体中，并向其中添加所需的控件。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="9fa0d-112">有关详细信息，请参阅[如何： 从命令行创建 Windows 窗体应用程序](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md)和[Windows 窗体上使用的控件](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="9fa0d-113">添加对的引用<xref:Microsoft.Win32>到你的代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="9fa0d-114">将以下代码添加到窗体必需的事件处理程序挂钩，并更改窗体所用的默认字体的构造函数。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="9fa0d-115">实现的处理程序<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>促使自动缩放窗体的事件时<xref:Microsoft.Win32.UserPreferenceCategory.Window>类别更改。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="9fa0d-116">最后，实现的处理程序<xref:System.Windows.Forms.Form.FormClosing>分离的事件<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fa0d-117">不包括此代码将导致应用程序泄漏内存。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  <span data-ttu-id="9fa0d-118">编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="9fa0d-119">若要手动更改在 Windows XP 中的字体方案</span><span class="sxs-lookup"><span data-stu-id="9fa0d-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="9fa0d-120">在 Windows 窗体应用程序运行时，右键单击 Windows 桌面上，然后选择**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9fa0d-121">在**显示属性**对话框中，单击**外观**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="9fa0d-122">从**字体大小**下拉列表框中，选择新的字体大小。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="9fa0d-123">你将注意到该窗体，现在做出反应的桌面字体方案中运行时更改。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-123">You will notice that the form now reacts to run time changes in the desktop font scheme.</span></span> <span data-ttu-id="9fa0d-124">当用户更改之间**正常**，**大字体**，和**特大字体**，窗体更改字体，并正确缩放。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa0d-125">示例</span><span class="sxs-lookup"><span data-stu-id="9fa0d-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="9fa0d-126">在此代码示例 constructer 包含调用`InitializeComponent`，这是定义当在 Visual Studio 中创建一个新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="9fa0d-127">如果你在构建命令行上的应用程序，请删除此代码行。</span><span class="sxs-lookup"><span data-stu-id="9fa0d-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa0d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fa0d-128">See Also</span></span>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [<span data-ttu-id="9fa0d-129">Windows 窗体中的自动缩放</span><span class="sxs-lookup"><span data-stu-id="9fa0d-129">Automatic Scaling in Windows Forms</span></span>](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
