---
title: 如何：使用对齐线和 Windows 窗体中的网格排列控件
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: 3a295eadae854a2e1a982f18ec49570944cc999d
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303512"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="eec0b-102">如何：使用对齐线和 Windows 窗体中的网格排列控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="eec0b-103">使用 Visual Studio 的布局功能，可以精确地直接在窗体上控件的放置位置。</span><span class="sxs-lookup"><span data-stu-id="eec0b-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="eec0b-104">添加到窗体或窗体上移动的控件可以自动对齐到的行和列的 Windows 窗体设计器的网格中，或可以使用对齐线功能对齐控件。</span><span class="sxs-lookup"><span data-stu-id="eec0b-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eec0b-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="eec0b-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="eec0b-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="eec0b-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="eec0b-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="eec0b-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="eec0b-108">若要对齐到网格的所有控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="eec0b-109">选择**SnapToGrid**在 Windows 窗体设计器中的布局模式**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="eec0b-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="eec0b-110">有关详细信息，请参阅[选项对话框常规 Windows 窗体设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="eec0b-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span> <span data-ttu-id="eec0b-111">所有控件现在都对齐本身沿网格上的点。</span><span class="sxs-lookup"><span data-stu-id="eec0b-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="eec0b-112">可以通过就地锁定对齐到网格的各个控件。</span><span class="sxs-lookup"><span data-stu-id="eec0b-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="eec0b-113">但是，锁定后，它们不能移动或调整大小。</span><span class="sxs-lookup"><span data-stu-id="eec0b-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="eec0b-114">有关锁定控件的详细信息，请参阅[如何：控件锁定到 Windows 窗体](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="eec0b-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="eec0b-115">若要使用对齐线对齐控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="eec0b-116">选择**对齐线**在 Windows 窗体设计器中的布局模式**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="eec0b-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="eec0b-117">有关详细信息，请参见[演练：在 Windows 上排列控件窗体使用对齐线](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="eec0b-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="eec0b-118">现在可以使用对齐线对齐并排列窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="eec0b-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec0b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="eec0b-119">See also</span></span>
- <span data-ttu-id="eec0b-120">[通常，Windows 窗体设计器选项对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eec0b-120">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- [<span data-ttu-id="eec0b-121">演练：使用对齐线的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="eec0b-122">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
- [<span data-ttu-id="eec0b-123">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="eec0b-124">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="eec0b-125">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="eec0b-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="eec0b-126">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="eec0b-127">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="eec0b-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
