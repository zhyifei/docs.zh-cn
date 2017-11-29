---
title: "为 Windows 窗体上的控件提供辅助功能信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d7afc8cc67dc3a428e4995230345938075fbcc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="d6a1c-102">为 Windows 窗体上的控件提供辅助功能信息</span><span class="sxs-lookup"><span data-stu-id="d6a1c-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="d6a1c-103">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="d6a1c-104">示例包括适用于盲人的屏幕阅读器，还有声音输入实用功能，方便人们发出声音命令，而不使用鼠标或键盘。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="d6a1c-105">这些辅助工具与由 Windows 窗体控件公开的辅助功能属性相交互。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="d6a1c-106">这些属性为：</span><span class="sxs-lookup"><span data-stu-id="d6a1c-106">These properties are:</span></span>  
  
-   <span data-ttu-id="d6a1c-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="d6a1c-107">**AccessibilityObject**</span></span>  
  
-   <span data-ttu-id="d6a1c-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="d6a1c-108">**AccessibleDefaultActionDescription**</span></span>  
  
-   <span data-ttu-id="d6a1c-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="d6a1c-109">**AccessibleDescription**</span></span>  
  
-   <span data-ttu-id="d6a1c-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="d6a1c-110">**AccessibleName**</span></span>  
  
-   <span data-ttu-id="d6a1c-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="d6a1c-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="d6a1c-112">AccessibilityObject 属性</span><span class="sxs-lookup"><span data-stu-id="d6a1c-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="d6a1c-113">此只读属性包含 <xref:System.Windows.Forms.AccessibleObject> 实例。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="d6a1c-114">**AccessibleObject** 实现了 <xref:Accessibility.IAccessible> 接口，它提供了有关控件的说明、屏幕位置、导航功能和值的信息。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="d6a1c-115">在将控件添加到窗体时，设计器会设置此值。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="d6a1c-116">AccessibleDefaultActionDescription 属性</span><span class="sxs-lookup"><span data-stu-id="d6a1c-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="d6a1c-117">该字符串描述控件的操作。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-117">This string describes the action of the control.</span></span> <span data-ttu-id="d6a1c-118">它不显示在“属性”窗口中，可能只在代码中被设置。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="d6a1c-119">下面的示例为按钮控件设置此属性：</span><span class="sxs-lookup"><span data-stu-id="d6a1c-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="d6a1c-120">AccessibleDescription 属性</span><span class="sxs-lookup"><span data-stu-id="d6a1c-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="d6a1c-121">该字符串描述控件。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-121">This string describes the control.</span></span> <span data-ttu-id="d6a1c-122">它可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6a1c-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="d6a1c-123">AccessibleName 属性</span><span class="sxs-lookup"><span data-stu-id="d6a1c-123">AccessibleName Property</span></span>  
 <span data-ttu-id="d6a1c-124">这是报告给辅助工具的控件名称。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="d6a1c-125">它可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6a1c-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="d6a1c-126">AccessibleRole 属性</span><span class="sxs-lookup"><span data-stu-id="d6a1c-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="d6a1c-127">此属性描述控件的用户接口角色，其中包含 <xref:System.Windows.Forms.AccessibleRole> 枚举。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="d6a1c-128">新的控件的值设置为 `Default`。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="d6a1c-129">这就意味着默认情况下， **Button** 控件充当 **按钮**。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="d6a1c-130">如果控件具有另一个角色，你可能希望重置此属性。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="d6a1c-131">例如，你可能正将 **PictureBox** 控件用作“图表” ，并且可能希望辅助工具将角色报告为“图表” ，而非 **PictureBox**。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="d6a1c-132">你可能还希望为已开发的自定义控件指定此属性。</span><span class="sxs-lookup"><span data-stu-id="d6a1c-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="d6a1c-133">此属性可能在“属性”窗口或代码中被设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6a1c-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a1c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6a1c-134">See Also</span></span>  
 <xref:System.Windows.Forms.AccessibleObject>  
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.AccessibleRole>
