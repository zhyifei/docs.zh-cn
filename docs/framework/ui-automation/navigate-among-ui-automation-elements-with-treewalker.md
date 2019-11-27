---
title: 使用 TreeWalker 在 UI 自动化元素之间导航
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 5c14a660481ed14c0d9f379c80f2d6934a3b6dcb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443167"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="4f759-102">使用 TreeWalker 在 UI 自动化元素之间导航</span><span class="sxs-lookup"><span data-stu-id="4f759-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="4f759-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="4f759-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4f759-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="4f759-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="4f759-105">本主题包含示例代码，该代码演示如何使用 <xref:System.Windows.Automation.TreeWalker> 类在 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 元素之间导航。</span><span class="sxs-lookup"><span data-stu-id="4f759-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f759-106">示例</span><span class="sxs-lookup"><span data-stu-id="4f759-106">Example</span></span>  
 <span data-ttu-id="4f759-107">下面的示例使用 <xref:System.Windows.Automation.TreeWalker.GetParent%2A> 向上遍历 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 树，直到找到根元素或桌面。</span><span class="sxs-lookup"><span data-stu-id="4f759-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="4f759-108">紧靠下面的元素，它是指定元素的父窗口。</span><span class="sxs-lookup"><span data-stu-id="4f759-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="4f759-109">示例</span><span class="sxs-lookup"><span data-stu-id="4f759-109">Example</span></span>  
 <span data-ttu-id="4f759-110">下面的示例使用 <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> 和 <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> 来创建一个 <xref:System.Windows.Forms.TreeView>，该显示控件视图中和已启用的 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 元素的整个子树。</span><span class="sxs-lookup"><span data-stu-id="4f759-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="4f759-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f759-111">See also</span></span>

- [<span data-ttu-id="4f759-112">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="4f759-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
