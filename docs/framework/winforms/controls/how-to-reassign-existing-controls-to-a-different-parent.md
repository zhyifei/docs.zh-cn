---
title: 如何：将现有的控件重新分配给不同的父控件
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 113afc642ca313f10062a496d2f170e3666d5043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162236"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="fb4bc-102">如何：将现有的控件重新分配给不同的父控件</span><span class="sxs-lookup"><span data-stu-id="fb4bc-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="fb4bc-103">可以将你窗体中的控件分配到新容器控件。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb4bc-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fb4bc-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fb4bc-106">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="fb4bc-107">若要将现有的控件重新分配给不同的父控件</span><span class="sxs-lookup"><span data-stu-id="fb4bc-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="fb4bc-108">将三个 <xref:System.Windows.Forms.Button> 控件从“工具箱”  拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="fb4bc-109">将其相邻放置，但不用对齐它们。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="fb4bc-110">在“工具箱” 中，单击 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="fb4bc-111">请勿将该图标拖动到窗体上。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="fb4bc-112">将鼠标指针移至靠近这 3 个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="fb4bc-113">指针更改为十字线时就会附上 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="fb4bc-114">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="fb4bc-115">拖动鼠标指针以绘制 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的轮廓。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="fb4bc-116">在这三个 <xref:System.Windows.Forms.Button> 控件周围绘制轮廓。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="fb4bc-117">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="fb4bc-118">这三种 <xref:System.Windows.Forms.Button> 控件现在插入到 <xref:System.Windows.Forms.FlowLayoutPanel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="fb4bc-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4bc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb4bc-119">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="fb4bc-120">排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="fb4bc-120">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="fb4bc-121">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="fb4bc-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="fb4bc-122">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="fb4bc-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
