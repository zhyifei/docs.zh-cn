---
title: "NumericUpDown 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1afb128fd5e098a59fa2636f09998a2a463c926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a><span data-ttu-id="afba7-102">NumericUpDown 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="afba7-102">NumericUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="afba7-103"><xref:System.Windows.Forms.NumericUpDown>控件看起来像一对用户可以单击来调整值的箭头和一个文本框的组合。</span><span class="sxs-lookup"><span data-stu-id="afba7-103">The <xref:System.Windows.Forms.NumericUpDown> control looks like a combination of a text box and a pair of arrows that the user can click to adjust a value.</span></span> <span data-ttu-id="afba7-104">该控件显示，并从一组固定数字值选项的设置的单个数值。</span><span class="sxs-lookup"><span data-stu-id="afba7-104">The control displays and sets a single numeric value from a list of fixed numeric-value choices.</span></span> <span data-ttu-id="afba7-105">用户可以增加和减少的数量，通过单击向上和向下箭头，按向上和向下箭头键，或通过控件的文本框部分中键入一个数字。</span><span class="sxs-lookup"><span data-stu-id="afba7-105">The user can increase and decrease the number by clicking the up and down arrows, by pressing the UP and DOWN ARROW keys, or by typing a number in the text box part of the control.</span></span> <span data-ttu-id="afba7-106">单击向上箭头键移动朝着最大值; 数单击向下箭头键来移动朝着最小值的数量。</span><span class="sxs-lookup"><span data-stu-id="afba7-106">Clicking the UP ARROW key moves the number toward the maximum; clicking the DOWN ARROW key moves the number toward the minimum.</span></span>  
  
 <span data-ttu-id="afba7-107">因为其通用的功能，而此控件的本质就是选择，例如，如果你想要创建音乐播放器应用程序的卷控件。</span><span class="sxs-lookup"><span data-stu-id="afba7-107">Because of its versatile functionality, this control is an obvious choice, for example, if you want to create a volume control for a music player application.</span></span> <span data-ttu-id="afba7-108"><xref:System.Windows.Forms.NumericUpDown>控件用于在许多 Windows 控制面板应用程序。</span><span class="sxs-lookup"><span data-stu-id="afba7-108">The <xref:System.Windows.Forms.NumericUpDown> control is used in many Windows Control Panel applications.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="afba7-109">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="afba7-109">Key Properties and Methods</span></span>  
 <span data-ttu-id="afba7-110">在控件的文本框中显示的数字可为各种格式，包括十六进制。</span><span class="sxs-lookup"><span data-stu-id="afba7-110">The numbers displayed in the control's text box can be in a variety of formats, including hexadecimal.</span></span> <span data-ttu-id="afba7-111">有关详细信息，请参阅[如何： 设置 Windows 窗体 NumericUpDown 控件的格式](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)。</span><span class="sxs-lookup"><span data-stu-id="afba7-111">For more information, see [How to: Set the Format for the Windows Forms NumericUpDown Control](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span></span> <span data-ttu-id="afba7-112">控件的主要属性包括<xref:System.Windows.Forms.NumericUpDown.Value%2A>， <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> （默认值为 100）， <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> （默认值为 0） 和<xref:System.Windows.Forms.NumericUpDown.Increment%2A>（默认值为 1）。</span><span class="sxs-lookup"><span data-stu-id="afba7-112">The key properties of the control are <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (default value 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (default value 0), and <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (default value 1).</span></span> <span data-ttu-id="afba7-113"><xref:System.Windows.Forms.NumericUpDown.Value%2A>属性设置在控件中选定的当前数目。</span><span class="sxs-lookup"><span data-stu-id="afba7-113">The <xref:System.Windows.Forms.NumericUpDown.Value%2A> property sets the current number selected in the control.</span></span> <span data-ttu-id="afba7-114"><xref:System.Windows.Forms.NumericUpDown.Increment%2A>属性设置为当用户单击向上或向下箭头，调整数的量。</span><span class="sxs-lookup"><span data-stu-id="afba7-114">The <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property sets the amount that the number is adjusted by when the user clicks an up or down arrow.</span></span> <span data-ttu-id="afba7-115">当焦点移出该控件时，将根据最小和最大的数字值验证键入的输入。</span><span class="sxs-lookup"><span data-stu-id="afba7-115">When focus moves off the control, any typed input will be validated against the minimum and maximum numeric values.</span></span> <span data-ttu-id="afba7-116">你可以增加控件在用户连续按向上或向下箭头，在数字上移动的速度与<xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="afba7-116">You can increase the speed that the control moves through numbers, when the user continuously presses the up or down arrow, with the <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> property.</span></span> <span data-ttu-id="afba7-117">控件的主要方法是<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>和<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>。</span><span class="sxs-lookup"><span data-stu-id="afba7-117">The key methods of the control are <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afba7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afba7-118">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="afba7-119">NumericUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="afba7-119">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="afba7-120">如何：设置 Windows 窗体 NumericUpDown 控件的格式</span><span class="sxs-lookup"><span data-stu-id="afba7-120">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [<span data-ttu-id="afba7-121">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="afba7-121">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
