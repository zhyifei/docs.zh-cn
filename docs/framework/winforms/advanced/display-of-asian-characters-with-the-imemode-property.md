---
title: "通过 ImeMode 属性显示亚洲字符"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ba86b0c1343d84e65f0e3f9ff48a09b3a80a27a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>通过 ImeMode 属性显示亚洲字符
<xref:System.Windows.Forms.Control.ImeMode%2A>属性使用的窗体和控件，以强制进行输入的法编辑器 (IME) 的特定模式。 IME 是编写中文、日语和朝鲜语脚本的必备组件，因为这些编写系统具有的字符多于常规键盘可编码的字符。 例如，可能想在特定文本框中仅允许使用 ASCII 字符。 在这种情况下可以设置<xref:System.Windows.Forms.Control.ImeMode%2A>属性<xref:System.Windows.Forms.ImeMode>并且用户将只能为该特定文本框中输入 ASCII 字符。 默认值<xref:System.Windows.Forms.Control.ImeMode%2A>属性是<xref:System.Windows.Forms.ImeMode>，因此如果你设置窗体的属性，在窗体上的所有控件将都继承该设置。 有关详细信息，请参阅<xref:System.Windows.Forms.Control.ImeMode%2A>) 和<xref:System.Windows.Forms.ImeMode>。  
  
## <a name="see-also"></a>另请参阅  
 [全球化 Windows 窗体](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
