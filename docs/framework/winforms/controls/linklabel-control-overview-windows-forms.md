---
title: LinkLabel 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 40326a9055ff51efae5f4c64744d0966870c6f6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535007"
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="fd64a-102">LinkLabel 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="fd64a-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="fd64a-103">Windows 窗体<xref:System.Windows.Forms.LinkLabel>控件，可将 Web 样式的链接添加到 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd64a-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="fd64a-104">你可以使用<xref:System.Windows.Forms.LinkLabel>控件可以使用的所有操作都<xref:System.Windows.Forms.Label>控制; 也可以设置为文件、 文件夹或网页的链接的文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd64a-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you also can set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="fd64a-105">如何使用 LinkLabel 控件</span><span class="sxs-lookup"><span data-stu-id="fd64a-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="fd64a-106">除了所有属性、 方法和事件的<xref:System.Windows.Forms.Label>控件，<xref:System.Windows.Forms.LinkLabel>控件具有超链接和链接颜色的属性。</span><span class="sxs-lookup"><span data-stu-id="fd64a-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="fd64a-107"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性设置的激活链接的文本的区域。</span><span class="sxs-lookup"><span data-stu-id="fd64a-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="fd64a-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>， <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>，和<xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A>属性设置的链接的颜色。</span><span class="sxs-lookup"><span data-stu-id="fd64a-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="fd64a-109"><xref:System.Windows.Forms.LinkLabel.LinkClicked>事件确定当选中此链接文本时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="fd64a-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="fd64a-110">最简单用法<xref:System.Windows.Forms.LinkLabel>控件将显示单个链接使用<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性，但你还可以显示多个超链接使用<xref:System.Windows.Forms.LinkLabel.Links%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fd64a-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="fd64a-111"><xref:System.Windows.Forms.LinkLabel.Links%2A>属性使您能够访问的链接集合。</span><span class="sxs-lookup"><span data-stu-id="fd64a-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="fd64a-112">你还可以指定中的数据<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>的每个单独的属性<xref:System.Windows.Forms.LinkLabel.Link>对象。</span><span class="sxs-lookup"><span data-stu-id="fd64a-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="fd64a-113">值<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>属性可以用于存储到显示的文件的位置或 Web 站点的地址。</span><span class="sxs-lookup"><span data-stu-id="fd64a-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd64a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd64a-114">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="fd64a-115">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="fd64a-115">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="fd64a-116">如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页</span><span class="sxs-lookup"><span data-stu-id="fd64a-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="fd64a-117">如何：更改 Windows 窗体 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="fd64a-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
