---
title: 如何：对 Windows 窗体上的对象分层
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 6000adeffcc991557e046461f93fec24e1262f54
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651676"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="7defc-102">如何：对 Windows 窗体上的对象分层</span><span class="sxs-lookup"><span data-stu-id="7defc-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="7defc-103">当您创建复杂的用户界面，或使用多文档界面 (MDI) 窗体时，通常想要层控件和子窗体以创建更复杂的用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="7defc-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="7defc-104">若要移动跟踪的控件和 windows 组的上下文中，可操作其 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="7defc-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="7defc-105">*Z 顺序*是沿窗体的 z 轴 （深度） 窗体上控件的可视化分层。</span><span class="sxs-lookup"><span data-stu-id="7defc-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="7defc-106">在窗口顶部的 z 顺序重叠所有其他窗口之上。</span><span class="sxs-lookup"><span data-stu-id="7defc-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="7defc-107">所有其他窗口重叠窗口底部的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="7defc-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7defc-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="7defc-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7defc-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="7defc-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7defc-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="7defc-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="7defc-111">在设计时排列控件</span><span class="sxs-lookup"><span data-stu-id="7defc-111">To layer controls at design time</span></span>  
  
1. <span data-ttu-id="7defc-112">选择你想要层的控件。</span><span class="sxs-lookup"><span data-stu-id="7defc-112">Select a control that you want to layer.</span></span>  
  
2. <span data-ttu-id="7defc-113">上**格式**菜单，依次指向**顺序**，然后单击**置于顶层**或者**发送回**。</span><span class="sxs-lookup"><span data-stu-id="7defc-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="7defc-114">若要以编程方式对控件进行分层</span><span class="sxs-lookup"><span data-stu-id="7defc-114">To layer controls programmatically</span></span>  
  
- <span data-ttu-id="7defc-115">使用<xref:System.Windows.Forms.Control.BringToFront%2A>和<xref:System.Windows.Forms.Control.SendToBack%2A>操作控件的 z 顺序的方法。</span><span class="sxs-lookup"><span data-stu-id="7defc-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="7defc-116">例如，如果<xref:System.Windows.Forms.TextBox>控件， `txtFirstName`，是其下方另一个控件，并想要将其放在顶部，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="7defc-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="7defc-117">Windows 窗体支持*控件包含*。</span><span class="sxs-lookup"><span data-stu-id="7defc-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="7defc-118">控件包含涉及到将放置多个控件内包含的控件，例如的数目<xref:System.Windows.Forms.RadioButton>控件的<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7defc-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="7defc-119">然后可以层中包含的控件的控件。</span><span class="sxs-lookup"><span data-stu-id="7defc-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="7defc-120">移动分组框移动，这些控件，因为它们包含其内部。</span><span class="sxs-lookup"><span data-stu-id="7defc-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7defc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7defc-121">See also</span></span>

- [<span data-ttu-id="7defc-122">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7defc-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="7defc-123">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="7defc-123">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="7defc-124">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="7defc-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="7defc-125">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="7defc-125">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="7defc-126">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7defc-126">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
