---
title: "如何：将控件锁定到 Windows 窗体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0bd0f8dcde95dcbb5ef8fcf398256b6931859c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="bd793-102">如何：将控件锁定到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="bd793-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="bd793-103">设计 Windows 应用程序的用户界面 (UI)，便可锁定控件后它们正确定位，以便不会无意中移动，或调整其大小设置其他属性时。</span><span class="sxs-lookup"><span data-stu-id="bd793-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="bd793-104">此外，你可以锁定和解锁所有窗体的控件，这将很多控件与窗体的有用，或可以解锁单独的控件。</span><span class="sxs-lookup"><span data-stu-id="bd793-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="bd793-105">一旦你已放置所有控件放置在所需窗体上，将其锁定所有的位置，以防止错误的移动。</span><span class="sxs-lookup"><span data-stu-id="bd793-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd793-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="bd793-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bd793-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="bd793-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bd793-108">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="bd793-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="bd793-109">要锁定控件</span><span class="sxs-lookup"><span data-stu-id="bd793-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="bd793-110">在**属性**窗口中，单击**锁定**属性并选择`true`。</span><span class="sxs-lookup"><span data-stu-id="bd793-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="bd793-111">（双击名称切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="bd793-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="bd793-112">或者，右击该控件并选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="bd793-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd793-113">锁定控件可以防止它们设计图面上拖动到新的大小或位置。</span><span class="sxs-lookup"><span data-stu-id="bd793-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="bd793-114">但是，你仍可以更改的大小或通过控件的位置**属性**窗口或代码中。</span><span class="sxs-lookup"><span data-stu-id="bd793-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="bd793-115">若要锁定窗体上的所有控件</span><span class="sxs-lookup"><span data-stu-id="bd793-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="bd793-116">从**格式**菜单上，选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="bd793-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd793-117">此命令锁定窗体的大小，因为窗体是控件。</span><span class="sxs-lookup"><span data-stu-id="bd793-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="bd793-118">若要解锁所有锁定窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="bd793-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="bd793-119">从**格式**菜单上，选择**锁定控件**。</span><span class="sxs-lookup"><span data-stu-id="bd793-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="bd793-120">窗体上的所有以前锁定的控件现解锁。</span><span class="sxs-lookup"><span data-stu-id="bd793-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="bd793-121">若要单独解锁锁定的控件</span><span class="sxs-lookup"><span data-stu-id="bd793-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="bd793-122">在**属性**窗口中，单击**锁定**属性并选择`false`。</span><span class="sxs-lookup"><span data-stu-id="bd793-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="bd793-123">（双击名称切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="bd793-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd793-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd793-124">See Also</span></span>  
 [<span data-ttu-id="bd793-125">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bd793-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="bd793-126">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="bd793-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="bd793-127">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="bd793-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="bd793-128">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="bd793-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="bd793-129">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bd793-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
