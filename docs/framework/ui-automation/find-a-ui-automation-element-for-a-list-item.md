---
title: 查找列表项的 UI 自动化元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741751"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="a294e-102">查找列表项的 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="a294e-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="a294e-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="a294e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a294e-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="a294e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a294e-105">本主题演示如何在已知项的索引时检索列表中项的 <xref:System.Windows.Automation.AutomationElement>。</span><span class="sxs-lookup"><span data-stu-id="a294e-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a294e-106">示例</span><span class="sxs-lookup"><span data-stu-id="a294e-106">Example</span></span>  
 <span data-ttu-id="a294e-107">下面的示例演示了两种从列表中检索指定项的方式，一个使用 <xref:System.Windows.Automation.TreeWalker>，另一个使用 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>。</span><span class="sxs-lookup"><span data-stu-id="a294e-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="a294e-108">第一种方法往往更快，适用于 Win32 控件，但第二种方法更快 Windows Presentation Foundation （WPF）控件。</span><span class="sxs-lookup"><span data-stu-id="a294e-108">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="a294e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a294e-109">See also</span></span>

- [<span data-ttu-id="a294e-110">获取 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="a294e-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
