---
title: 如何：打开消息框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123722"
---
# <a name="how-to-open-a-message-box"></a>如何：打开消息框
此示例演示如何打开消息框。  
  
## <a name="example"></a>示例  
 消息框是用于向用户显示信息的预制模式对话框。 通过调用 <xref:System.Windows.MessageBox> 类的静态 <xref:System.Windows.MessageBox.Show%2A> 方法打开一个消息框。 调用 <xref:System.Windows.MessageBox.Show%2A> 时，消息是使用字符串参数传递的。 <xref:System.Windows.MessageBox.Show%2A> 的多个重载使你可以配置消息框的显示方式（请参阅 <xref:System.Windows.MessageBox>）。  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>另请参阅

- [MessageBox 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
