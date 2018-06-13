---
title: 如何：将控件锁定到 Windows 窗体
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: f05da53f134f13bf5edbbe7ab8c5973f79bbca4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534740"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="2a8c7-102">如何：将控件锁定到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="2a8c7-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="2a8c7-103">设计 Windows 应用程序的用户界面 (UI)，便可锁定控件后它们正确定位，以便不会无意中移动，或调整其大小设置其他属性时。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="2a8c7-104">此外，你可以锁定和解锁所有窗体的控件，这将很多控件与窗体的有用，或可以解锁单独的控件。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="2a8c7-105">一旦你已放置所有控件放置在所需窗体上，将其锁定所有的位置，以防止错误的移动。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a8c7-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2a8c7-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2a8c7-108">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="2a8c7-109">要锁定控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="2a8c7-110">在**属性**窗口中，单击**锁定**属性并选择`true`。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="2a8c7-111">（双击名称切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="2a8c7-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="2a8c7-112">或者，右击该控件并选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a8c7-113">锁定控件可以防止它们设计图面上拖动到新的大小或位置。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="2a8c7-114">但是，你仍可以更改的大小或通过控件的位置**属性**窗口或代码中。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="2a8c7-115">若要锁定窗体上的所有控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="2a8c7-116">从**格式**菜单上，选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a8c7-117">此命令锁定窗体的大小，因为窗体是控件。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="2a8c7-118">若要解锁所有锁定窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="2a8c7-119">从**格式**菜单上，选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="2a8c7-120">窗体上的所有以前锁定的控件现解锁。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="2a8c7-121">若要单独解锁锁定的控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="2a8c7-122">在**属性**窗口中，单击**锁定**属性并选择`false`。</span><span class="sxs-lookup"><span data-stu-id="2a8c7-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="2a8c7-123">（双击名称切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="2a8c7-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8c7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a8c7-124">See Also</span></span>  
 [<span data-ttu-id="2a8c7-125">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="2a8c7-126">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="2a8c7-127">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="2a8c7-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="2a8c7-128">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="2a8c7-129">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="2a8c7-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
