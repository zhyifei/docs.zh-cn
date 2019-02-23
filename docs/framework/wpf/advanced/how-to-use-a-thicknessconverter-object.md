---
title: 如何：使用 ThicknessConverter 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 653137c0707c2b7ee51f6bdac6bb2501f1845e1a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747338"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="72608-102">如何：使用 ThicknessConverter 对象</span><span class="sxs-lookup"><span data-stu-id="72608-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="72608-103">示例</span><span class="sxs-lookup"><span data-stu-id="72608-103">Example</span></span>  
 <span data-ttu-id="72608-104">此示例演示如何创建的实例<xref:System.Windows.ThicknessConverter>并使用它来更改边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="72608-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="72608-105">该示例定义一个名为的自定义方法`changeThickness`; 此方法首先将转换的内容<xref:System.Windows.Controls.ListBoxItem>在单独的定义，[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件的实例<xref:System.Windows.Thickness>，和更高版本将转换到的内容<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="72608-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="72608-106">此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.ThicknessConverter>对象，它将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>的实例<xref:System.Windows.Thickness>。</span><span class="sxs-lookup"><span data-stu-id="72608-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="72608-107">然后将此值传递的值为<xref:System.Windows.Controls.Border.BorderThickness%2A>属性的<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="72608-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="72608-108">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="72608-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="72608-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="72608-109">See also</span></span>
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="72608-110">[如何：更改边距属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72608-110">[How to: Change the Margin Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="72608-111">[如何：将 ListBoxItem 转换为新的数据类型](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72608-111">[How to: Convert a ListBoxItem to a new Data Type](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="72608-112">面板概述</span><span class="sxs-lookup"><span data-stu-id="72608-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
