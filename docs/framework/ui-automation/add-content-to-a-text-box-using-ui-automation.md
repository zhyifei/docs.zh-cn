---
title: 使用 UI 自动化向文本框添加内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 71385690c01d261b4ff1b495674bab377232e81d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447259"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>使用 UI 自动化向文本框添加内容
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题包含示例代码，该代码演示如何使用 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 将文本插入单行文本框中。 为多行和多格式文本控件提供了一个替代方法，其中 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 不适用。 出于比较目的，此示例还演示了如何使用 Win32 方法来实现相同的结果。  
  
## <a name="example"></a>示例  
 下面的示例逐步介绍目标应用程序中的一系列文本控件。 将对每个文本控件进行测试，以查看是否可以使用 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 方法从 <xref:System.Windows.Automation.ValuePattern> 对象获取该对象。 如果文本控件确实支持 <xref:System.Windows.Automation.ValuePattern>，则 <xref:System.Windows.Automation.ValuePattern.SetValue%2A> 方法用于将用户定义的字符串插入到文本控件中。 否则，使用 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> 方法。  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>另请参阅

- [TextPattern 插入文本示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
