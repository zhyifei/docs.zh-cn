---
title: 如何：定义 GroupBox 模板
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: ed66d51e87a25f74e646d0d535ac9e4ee9c8a056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551131"
---
# <a name="how-to-define-a-groupbox-template"></a>如何：定义 GroupBox 模板
此示例演示如何为创建模板<xref:System.Windows.Controls.GroupBox>控件。  
  
## <a name="example"></a>示例  
 下面的示例定义<xref:System.Windows.Controls.GroupBox>使用控件模板<xref:System.Windows.Controls.Grid>布局的控件。 该模板使用<xref:System.Windows.Controls.BorderGapMaskConverter>定义的边框<xref:System.Windows.Controls.GroupBox>以便边框不遮盖<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>内容。  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.GroupBox>  
 [GroupBox 操作方法主题](http://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
