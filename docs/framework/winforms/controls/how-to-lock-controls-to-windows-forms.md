---
title: 锁定控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736232"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="37f7a-102">如何：将控件锁定到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="37f7a-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="37f7a-103">设计 Windows 应用程序的用户界面（UI）时，可以在控件定位正确之后锁定控件，以便在设置其他属性时不会无意中移动或调整它们的大小。</span><span class="sxs-lookup"><span data-stu-id="37f7a-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="37f7a-104">此外，您还可以同时锁定和解锁窗体上的所有控件，这对于具有许多控件的窗体非常有用，或者您可以对各个控件解除锁定。</span><span class="sxs-lookup"><span data-stu-id="37f7a-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="37f7a-105">将所有控件置于窗体上所需的位置后，请将它们全部锁定，以防错误移动。</span><span class="sxs-lookup"><span data-stu-id="37f7a-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="37f7a-106">锁定控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-106">To lock a control</span></span>

<span data-ttu-id="37f7a-107">在 Visual Studio 的 "**属性**" 窗口中，选择 "**锁定**" 属性，然后选择 " **true**"。</span><span class="sxs-lookup"><span data-stu-id="37f7a-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="37f7a-108">（双击该名称将切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="37f7a-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="37f7a-109">或者，右键单击控件，然后选择 "**锁定控件**"。</span><span class="sxs-lookup"><span data-stu-id="37f7a-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="37f7a-110">锁定控件可防止将其拖动到设计图面上的新大小或位置。</span><span class="sxs-lookup"><span data-stu-id="37f7a-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="37f7a-111">但是，您仍然可以通过 "**属性**" 窗口或代码来更改控件的大小或位置。</span><span class="sxs-lookup"><span data-stu-id="37f7a-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="37f7a-112">锁定窗体上的所有控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-112">To lock all the controls on a form</span></span>

<span data-ttu-id="37f7a-113">从 "**格式**" 菜单中选择 "**锁定控件**"。</span><span class="sxs-lookup"><span data-stu-id="37f7a-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="37f7a-114">此命令也会锁定窗体的大小，因为窗体是一个控件。</span><span class="sxs-lookup"><span data-stu-id="37f7a-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="37f7a-115">解锁窗体上的所有锁定控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="37f7a-116">从 "**格式**" 菜单中选择 "**锁定控件**"。</span><span class="sxs-lookup"><span data-stu-id="37f7a-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="37f7a-117">窗体上所有以前锁定的控件现在都未被锁定。</span><span class="sxs-lookup"><span data-stu-id="37f7a-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="37f7a-118">单独解锁锁定的控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-118">To unlock locked controls individually</span></span>

<span data-ttu-id="37f7a-119">在 "**属性**" 窗口中，选择 "**锁定**" 属性，然后选择 " **false**"。</span><span class="sxs-lookup"><span data-stu-id="37f7a-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="37f7a-120">（双击该名称将切换属性设置。）</span><span class="sxs-lookup"><span data-stu-id="37f7a-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="37f7a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37f7a-121">See also</span></span>

- [<span data-ttu-id="37f7a-122">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="37f7a-123">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="37f7a-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="37f7a-124">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="37f7a-125">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="37f7a-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
