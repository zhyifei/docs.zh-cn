---
title: "如何：使用系统字体键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18781e3d71b9b30352323081e6d938350c6e53d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-fonts-keys"></a>如何：使用系统字体键
系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemFonts>是一个类，包含系统字体值和绑定到这些值的系统字体资源-例如，<xref:System.Windows.SystemFonts.CaptionFontFamily%2A>和<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>。  
  
 系统字体规格可用作静态或动态资源。 如果希望字体规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。  
  
> [!NOTE]
>  动态资源具有关键字*密钥*追加到属性名称。  
  
 以下示例演示如何访问和使用系统字体动态资源来设计按钮样式或自定义按钮。 这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例创建一个将分配的按钮样式<xref:System.Windows.SystemFonts>至一个按钮的值。  
  
## <a name="example"></a>示例  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>另请参阅  
 [使用系统画笔绘制区域](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [使用 SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [使用 SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
