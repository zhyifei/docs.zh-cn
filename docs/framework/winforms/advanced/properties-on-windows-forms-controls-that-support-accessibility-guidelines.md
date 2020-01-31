---
title: 控件的辅助功能属性
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743427"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="e5219-102">내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="e5219-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="e5219-103">Windows 窗体的标准工具箱中的控件支持许多辅助功能准则，包括公开键盘焦点并公开屏幕元素。</span><span class="sxs-lookup"><span data-stu-id="e5219-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="e5219-104">提前规划辅助功能</span><span class="sxs-lookup"><span data-stu-id="e5219-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="e5219-105">控件的属性可用于支持其他辅助功能准则，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e5219-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="e5219-106">此外，还应使用菜单提供对程序功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e5219-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="e5219-107">控件属性</span><span class="sxs-lookup"><span data-stu-id="e5219-107">Control Property</span></span>|<span data-ttu-id="e5219-108">辅助功能注意事项</span><span class="sxs-lookup"><span data-stu-id="e5219-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="e5219-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="e5219-109">AccessibleDescription</span></span>|<span data-ttu-id="e5219-110">描述将报告给辅助工具，如屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="e5219-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="e5219-111">접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5219-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="e5219-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="e5219-112">AccessibleName</span></span>|<span data-ttu-id="e5219-113">将报告给辅助功能辅助工具的名称。</span><span class="sxs-lookup"><span data-stu-id="e5219-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="e5219-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="e5219-114">AccessibleRole</span></span>|<span data-ttu-id="e5219-115">介绍如何在用户界面中使用元素。</span><span class="sxs-lookup"><span data-stu-id="e5219-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="e5219-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="e5219-116">TabIndex</span></span>|<span data-ttu-id="e5219-117">通过窗体创建一个明智的导航路径。</span><span class="sxs-lookup"><span data-stu-id="e5219-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="e5219-118">对于没有内部标签的控件（如文本框），要使它们的关联标签在 tab 键顺序中紧挨着，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="e5219-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="e5219-119">텍스트</span><span class="sxs-lookup"><span data-stu-id="e5219-119">Text</span></span>|<span data-ttu-id="e5219-120">使用 "&" 字符创建访问密钥。</span><span class="sxs-lookup"><span data-stu-id="e5219-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="e5219-121">使用访问密钥是提供对功能的已记录的键盘访问。</span><span class="sxs-lookup"><span data-stu-id="e5219-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="e5219-122">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="e5219-122">Font Size</span></span>|<span data-ttu-id="e5219-123">如果字体大小不可调整，则应将其设置为10磅或更大。</span><span class="sxs-lookup"><span data-stu-id="e5219-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="e5219-124">设置窗体的字体大小后，此后添加到窗体的所有控件都将具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="e5219-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="e5219-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="e5219-125">Forecolor</span></span>|<span data-ttu-id="e5219-126">如果将此属性设置为默认值，则将在窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="e5219-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="e5219-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="e5219-127">Backcolor</span></span>|<span data-ttu-id="e5219-128">如果将此属性设置为默认值，则将在窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="e5219-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="e5219-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="e5219-129">BackgroundImage</span></span>|<span data-ttu-id="e5219-130">将此属性留空可使文本更具可读性。</span><span class="sxs-lookup"><span data-stu-id="e5219-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5219-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5219-131">See also</span></span>

- [<span data-ttu-id="e5219-132">연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="e5219-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)
