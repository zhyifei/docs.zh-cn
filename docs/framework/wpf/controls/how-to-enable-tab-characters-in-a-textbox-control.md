---
title: 如何：在 TextBox 控件中启用制表符
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 9a01ae93d1b75c604fbe4f15f720e0a84086bd1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910567"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>如何：在 TextBox 控件中启用制表符
此示例演示如何作为正常输入中启用制表符接受<xref:System.Windows.Controls.TextBox>控件。  
  
## <a name="example"></a>示例  
 若要启用的制表符字符数的接受作为输入<xref:System.Windows.Controls.TextBox>控件，将<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A>归于**true**。  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
