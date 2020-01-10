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
# <a name="find-a-ui-automation-element-for-a-list-item"></a>查找列表项的 UI 自动化元素
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题演示如何在已知项的索引时检索列表中项的 <xref:System.Windows.Automation.AutomationElement>。  
  
## <a name="example"></a>示例  
 下面的示例演示了两种从列表中检索指定项的方式，一个使用 <xref:System.Windows.Automation.TreeWalker>，另一个使用 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>。  
  
 第一种方法往往更快，适用于 Win32 控件，但第二种方法更快 Windows Presentation Foundation （WPF）控件。  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>另请参阅

- [获取 UI 自动化元素](obtaining-ui-automation-elements.md)
