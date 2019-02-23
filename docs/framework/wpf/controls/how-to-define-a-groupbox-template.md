---
title: 如何：定义 GroupBox 模板
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 6294a52d5914b52d191b564330f904e6a865c283
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745193"
---
# <a name="how-to-define-a-groupbox-template"></a>如何：定义 GroupBox 模板
此示例演示如何创建模板<xref:System.Windows.Controls.GroupBox>控件。  
  
## <a name="example"></a>示例  
 下面的示例定义<xref:System.Windows.Controls.GroupBox>通过使用控件模板<xref:System.Windows.Controls.Grid>布局的控制。 该模板使用<xref:System.Windows.Controls.BorderGapMaskConverter>定义的边框<xref:System.Windows.Controls.GroupBox>以便边框不会遮盖<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>内容。  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.GroupBox>
- [如何：创建分组框](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))
