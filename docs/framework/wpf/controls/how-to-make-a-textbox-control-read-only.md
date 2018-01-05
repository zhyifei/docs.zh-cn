---
title: "如何：将 TextBox 控件设为只读"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d3acf1e5065633f9f4c75f24780230525b01ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="05cb0-102">如何：将 TextBox 控件设为只读</span><span class="sxs-lookup"><span data-stu-id="05cb0-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="05cb0-103">此示例演示如何配置<xref:System.Windows.Controls.TextBox>控件不允许用户输入或修改。</span><span class="sxs-lookup"><span data-stu-id="05cb0-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05cb0-104">示例</span><span class="sxs-lookup"><span data-stu-id="05cb0-104">Example</span></span>  
 <span data-ttu-id="05cb0-105">若要防止用户修改的内容<xref:System.Windows.Controls.TextBox>控制、 设置<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>属性设为**true**。</span><span class="sxs-lookup"><span data-stu-id="05cb0-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="05cb0-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>特性影响仅用户输入; 它不会影响在中设置的文本[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]说明<xref:System.Windows.Controls.TextBox>控件或设置以编程方式通过文本<xref:System.Windows.Controls.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="05cb0-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="05cb0-107">默认值<xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>是**false**。</span><span class="sxs-lookup"><span data-stu-id="05cb0-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cb0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="05cb0-108">See Also</span></span>  
 [<span data-ttu-id="05cb0-109">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="05cb0-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="05cb0-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="05cb0-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
