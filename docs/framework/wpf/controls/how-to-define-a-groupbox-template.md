---
title: 如何：定义 GroupBox 模板
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: dd53af87ec2d12b2ed0dcf2b23374d76e8f631a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225711"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="0fec6-102">如何：定义 GroupBox 模板</span><span class="sxs-lookup"><span data-stu-id="0fec6-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="0fec6-103">此示例演示如何创建模板<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="0fec6-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fec6-104">示例</span><span class="sxs-lookup"><span data-stu-id="0fec6-104">Example</span></span>  
 <span data-ttu-id="0fec6-105">下面的示例定义<xref:System.Windows.Controls.GroupBox>通过使用控件模板<xref:System.Windows.Controls.Grid>布局的控制。</span><span class="sxs-lookup"><span data-stu-id="0fec6-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="0fec6-106">该模板使用<xref:System.Windows.Controls.BorderGapMaskConverter>定义的边框<xref:System.Windows.Controls.GroupBox>以便边框不会遮盖<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>内容。</span><span class="sxs-lookup"><span data-stu-id="0fec6-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="0fec6-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fec6-107">See also</span></span>

- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="0fec6-108">[如何：创建分组框](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0fec6-108">[How to: Create a GroupBox](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
