---
title: "如何：使用自动布局创建按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c642e6491722e9bfe35337d066e3870f5a70f38c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="0e4f6-102">如何：使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="0e4f6-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="0e4f6-103">本示例介绍如何使用自动布局方法在可本地化的应用程序中创建按钮。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="0e4f6-104">本地化[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]可能是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="0e4f6-105">通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="0e4f6-106">在过去每种语言，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]已适用于需要调整。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="0e4f6-107">现在使用的功能[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以设计减少必需的调整的元素。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="0e4f6-108">编写的应用程序可以更轻松地调整大小和重新定位的种方法称为`automatic layout`。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="0e4f6-109">以下两个[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例创建的应用程序实例化一个按钮; 另一个使用英文文本和一个具有西班牙语文本。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="0e4f6-110">请注意，除文本之外，代码都一样；按钮会配合文字进行调整。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e4f6-111">示例</span><span class="sxs-lookup"><span data-stu-id="0e4f6-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="0e4f6-112">下图显示代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="0e4f6-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="0e4f6-113">![具有不同语言的文本的同一按钮](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="0e4f6-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="0e4f6-114">自动调整大小的按钮</span><span class="sxs-lookup"><span data-stu-id="0e4f6-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4f6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e4f6-115">See Also</span></span>  
 [<span data-ttu-id="0e4f6-116">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="0e4f6-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="0e4f6-117">使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="0e4f6-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
