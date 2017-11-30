---
title: "如何：创建具有阴影的文本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>如何：创建具有阴影的文本
本节中的示例演示如何为所显示的文本创建阴影效果。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.Effects.DropShadowEffect>对象允许你创建的卷影效果的各种放[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]对象。 以下示例显示了应用于文本的投影效果。 在本例中，阴影是柔和阴影，这意味着阴影颜色模糊化。  
  
 ![使用柔和度 &#61; 的文本阴影0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
具有柔和阴影的文本的示例  
  
 你可以通过设置控制的卷影宽度<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>属性。 值为`4.0`指示阴影的宽度为 4 个像素。 你可以控制柔和度，或模糊的阴影通过修改<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性。 值为`0.0`指示无模糊。 以下代码示例演示如何创建柔和阴影。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  这些卷影效果不会[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本呈现管线。 因此，在使用这些效果时，将禁用 ClearType。  
  
 以下示例显示了应用于文本的硬投影效果。 在此例中，阴影不模糊。  
  
 ![使用柔和度 &#61; 的文本阴影0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
具有硬阴影的文本的示例  
  
 你可以通过设置创建硬阴影<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性`0.0`，指示是否使用的不模糊。 你可以通过修改控制的阴影方向<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性。 将此属性的方向的值设置为之间的度数`0`和`360`。 下图显示的方向值<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性设置。  
  
 ![阴影的 DropShadow 程度设置](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
DropShadow 方向示意图  
  
 以下代码示例演示如何创建硬阴影。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>使用模糊效果  
 A<xref:System.Windows.Media.Effects.BlurBitmapEffect>可以用于创建可以放置在文本对象后面的卷影类似的效果。 应用于文本的模糊位图效果在各个方向上均匀地对文本进行模糊化。  
  
 以下示例显示了应用于文本的模糊效果。  
  
 ![使用 BlurBitmapEffect 的文本阴影](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
具有模糊效果的文本的示例  
  
 以下代码示例演示如何创建模糊效果。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>使用转换变换  
 A<xref:System.Windows.Media.TranslateTransform>可以用于创建可以放置在文本对象后面的卷影类似的效果。  
  
 下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。 在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。  
  
 ![使用 TranslateTransform 的文本阴影](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
使用转换功能实现阴影效果的文本的示例  
  
 以下代码示例演示如何创建转换以实现阴影效果。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
