---
title: 如何：将 TextBox 控件设为只读
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517170"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>如何：将 TextBox 控件设为只读
此示例演示如何配置<xref:System.Windows.Controls.TextBox>控件不允许用户输入或修改。  
  
## <a name="example"></a>示例  
 若要防止用户修改的内容<xref:System.Windows.Controls.TextBox>控件，将<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>归于**true**。  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性会影响仅用户输入; 不会影响文本中设置[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的说明<xref:System.Windows.Controls.TextBox>控件或以编程方式通过设置文本<xref:System.Windows.Controls.TextBox.Text%2A>属性。  
  
 默认值<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>是**false**。  
  
## <a name="see-also"></a>请参阅
- [TextBox 概述](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox 概述](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
