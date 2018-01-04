---
title: "如何：使用 ThicknessConverter 对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 311998595cb1584c276afc28510e1750c770ae93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="33458-102">如何：使用 ThicknessConverter 对象</span><span class="sxs-lookup"><span data-stu-id="33458-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="33458-103">示例</span><span class="sxs-lookup"><span data-stu-id="33458-103">Example</span></span>  
 <span data-ttu-id="33458-104">此示例演示如何创建的实例<xref:System.Windows.ThicknessConverter>并使用它来更改边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="33458-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="33458-105">该示例定义的自定义的方法调用`changeThickness`; 此方法首先将内容转换<xref:System.Windows.Controls.ListBoxItem>，如在单独定义[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件、 实例<xref:System.Windows.Thickness>，和更高版本将转换到的内容<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="33458-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="33458-106">此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.ThicknessConverter>对象，后者将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到实例<xref:System.Windows.Thickness>。</span><span class="sxs-lookup"><span data-stu-id="33458-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="33458-107">此值然后传递的值作为<xref:System.Windows.Controls.Border.BorderThickness%2A>属性<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="33458-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="33458-108">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="33458-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="33458-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="33458-109">See Also</span></span>  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="33458-110">如何： 更改 Margin 属性</span><span class="sxs-lookup"><span data-stu-id="33458-110">How to: Change the Margin Property</span></span>](http://msdn.microsoft.com/en-us/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [<span data-ttu-id="33458-111">如何： 将 ListBoxItem 转换为新的数据类型</span><span class="sxs-lookup"><span data-stu-id="33458-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](http://msdn.microsoft.com/en-us/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [<span data-ttu-id="33458-112">面板概述</span><span class="sxs-lookup"><span data-stu-id="33458-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
