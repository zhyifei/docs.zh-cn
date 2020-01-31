---
title: StatusBar 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 4d48cf497eeedcff6290dfa8ddecf38ce8ff7c63
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742859"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="acc6f-102">StatusBar 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="acc6f-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="acc6f-103"><xref:System.Windows.Forms.ToolStripStatusLabel> 控件将替换功能并将其添加到 <xref:System.Windows.Forms.StatusBar> 控件;但是，如果您选择，则会保留 <xref:System.Windows.Forms.StatusBar> 控件以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="acc6f-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="acc6f-104">Windows Forms <xref:System.Windows.Forms.StatusBar> 컨트롤은 폼에서 애플리케이션이 다양한 종류의 상태 정보를 표시할 수 있는, 대개 창 아래쪽에 표시되는 영역으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acc6f-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="acc6f-105"><xref:System.Windows.Forms.StatusBar> 控件可以在其上具有状态栏面板，这些面板显示用于指示状态的图标，或动画中指示进程工作的一系列图标。例如，Microsoft Word 表明文档正在保存。</span><span class="sxs-lookup"><span data-stu-id="acc6f-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acc6f-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="acc6f-106">In This Section</span></span>  
 [<span data-ttu-id="acc6f-107">StatusBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="acc6f-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="acc6f-108">介绍 <xref:System.Windows.Forms.StatusBar> 控件的一般概念，该控件使用户能够查看具有焦点的控件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="acc6f-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="acc6f-109">방법: StatusBar 컨트롤에 패널 추가</span><span class="sxs-lookup"><span data-stu-id="acc6f-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="acc6f-110">说明如何向 <xref:System.Windows.Forms.StatusBar> 控件添加可编程面板。</span><span class="sxs-lookup"><span data-stu-id="acc6f-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="acc6f-111">방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인</span><span class="sxs-lookup"><span data-stu-id="acc6f-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="acc6f-112">说明如何处理从 <xref:System.Windows.Forms.StatusBar> 控件引发的 <xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="acc6f-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="acc6f-113">방법: 상태 표시줄 패널의 크기 설정</span><span class="sxs-lookup"><span data-stu-id="acc6f-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="acc6f-114">提供有关属性的详细信息，这些属性控制运行时状态栏面板的宽度和大小调整行为。</span><span class="sxs-lookup"><span data-stu-id="acc6f-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="acc6f-115">연습: 런타임에 상태 표시줄 정보 업데이트</span><span class="sxs-lookup"><span data-stu-id="acc6f-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="acc6f-116">说明如何以编程方式控制状态栏面板中的数据。</span><span class="sxs-lookup"><span data-stu-id="acc6f-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="acc6f-117">참조</span><span class="sxs-lookup"><span data-stu-id="acc6f-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="acc6f-118">클래스 및 해당 멤버에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acc6f-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="acc6f-119">替换 <xref:System.Windows.Forms.StatusBar> 控件并向其中添加功能。</span><span class="sxs-lookup"><span data-stu-id="acc6f-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="acc6f-120">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="acc6f-120">Related Sections</span></span>  
 [<span data-ttu-id="acc6f-121">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="acc6f-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="acc6f-122">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acc6f-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
