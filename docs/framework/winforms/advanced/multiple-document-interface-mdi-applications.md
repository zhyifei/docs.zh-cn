---
title: 多文档界面 (MDI) 应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956550"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="66583-102">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="66583-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="66583-103">多文档界面 (MDI) 应用程序使您能够同时显示多个文档, 每个文档都显示在其自己的窗口中。</span><span class="sxs-lookup"><span data-stu-id="66583-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="66583-104">MDI 应用程序通常具有一个带有子菜单的 "窗口" 菜单项, 用于在窗口或文档之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="66583-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66583-105">Windows 窗体中的 MDI 窗体和单文档界面 (SDI) 窗口之间存在一些行为差异。</span><span class="sxs-lookup"><span data-stu-id="66583-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="66583-106">`Opacity`属性不影响 MDI 子窗体的外观。</span><span class="sxs-lookup"><span data-stu-id="66583-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="66583-107">此外, 此<xref:System.Windows.Forms.Form.CenterToParent%2A>方法不会影响 MDI 子窗体的行为。</span><span class="sxs-lookup"><span data-stu-id="66583-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66583-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="66583-108">In This Section</span></span>  
 [<span data-ttu-id="66583-109">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="66583-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="66583-110">提供有关为 MDI 应用程序中的多个文档创建容器的说明。</span><span class="sxs-lookup"><span data-stu-id="66583-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="66583-111">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="66583-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="66583-112">提供有关创建在 MDI 父窗体中运行的一个或多个窗口的说明。</span><span class="sxs-lookup"><span data-stu-id="66583-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="66583-113">如何：确定活动的 MDI 子窗</span><span class="sxs-lookup"><span data-stu-id="66583-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="66583-114">为验证具有焦点的子窗口 (并将其内容发送到剪贴板) 提供说明。</span><span class="sxs-lookup"><span data-stu-id="66583-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="66583-115">如何：将数据发送到活动的 MDI 子级</span><span class="sxs-lookup"><span data-stu-id="66583-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="66583-116">提供将信息传输到活动子窗口的说明。</span><span class="sxs-lookup"><span data-stu-id="66583-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="66583-117">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="66583-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="66583-118">提供平铺、层叠或排列 MDI 应用程序的子窗口的说明。</span><span class="sxs-lookup"><span data-stu-id="66583-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
