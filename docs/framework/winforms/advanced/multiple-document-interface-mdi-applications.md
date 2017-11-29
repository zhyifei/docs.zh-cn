---
title: "多文档界面 (MDI) 应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c122931b0a00f487ddab07550913988462cfd50e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="7afe9-102">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="7afe9-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="7afe9-103">多文档界面 (MDI) 应用程序，可以在同一时间，每个文档显示在自己的窗口中显示多个文档。</span><span class="sxs-lookup"><span data-stu-id="7afe9-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="7afe9-104">MDI 应用程序通常具有窗口菜单项具有子菜单窗口或文档之间切换。</span><span class="sxs-lookup"><span data-stu-id="7afe9-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7afe9-105">有一些 MDI 窗体和单文档界面 (SDI) 的窗口之间 Windows 窗体中的行为差异。</span><span class="sxs-lookup"><span data-stu-id="7afe9-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="7afe9-106">`Opacity`属性不会影响 MDI 子窗体的外观。</span><span class="sxs-lookup"><span data-stu-id="7afe9-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="7afe9-107">此外，<xref:System.Windows.Forms.Form.CenterToParent%2A>方法不会影响 MDI 子窗体的行为。</span><span class="sxs-lookup"><span data-stu-id="7afe9-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7afe9-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="7afe9-108">In This Section</span></span>  
 [<span data-ttu-id="7afe9-109">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="7afe9-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="7afe9-110">提供有关如何创建在 MDI 应用程序的多个文档的容器。</span><span class="sxs-lookup"><span data-stu-id="7afe9-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="7afe9-111">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="7afe9-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="7afe9-112">提供用于创建在 MDI 父窗体中运行的一个或多个窗口的说明。</span><span class="sxs-lookup"><span data-stu-id="7afe9-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="7afe9-113">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="7afe9-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="7afe9-114">提供有关如何验证具有焦点的子窗口 （并将其内容发送到剪贴板）。</span><span class="sxs-lookup"><span data-stu-id="7afe9-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="7afe9-115">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="7afe9-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="7afe9-116">提供有关如何将信息传输到活动子窗口。</span><span class="sxs-lookup"><span data-stu-id="7afe9-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="7afe9-117">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="7afe9-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="7afe9-118">提供有关平铺、 层叠或排列的子窗口的 MDI 应用程序的指导。</span><span class="sxs-lookup"><span data-stu-id="7afe9-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
