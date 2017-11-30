---
title: "不在对象树中的对象元素的初始化"
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
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a2a4dd10b664dc349b0c413d7abac03280f8fb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a><span data-ttu-id="8792e-102">不在对象树中的对象元素的初始化</span><span class="sxs-lookup"><span data-stu-id="8792e-102">Initialization for Object Elements Not in an Object Tree</span></span>
<span data-ttu-id="8792e-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 初始化时某些方面会被推迟，在通常依赖连接到逻辑树或可视化树的元素的进程中执行。</span><span class="sxs-lookup"><span data-stu-id="8792e-103">Some aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] initialization are deferred to processes that typically rely on that element being connected to either the logical tree or visual tree.</span></span> <span data-ttu-id="8792e-104">本主题介绍了针对未连接到两种树之一的元素，将其初始化可能需要的步骤。</span><span class="sxs-lookup"><span data-stu-id="8792e-104">This topic describes the steps that may be necessary in order to initialize an element that is not connected to either tree.</span></span>  
  
 
  
## <a name="elements-and-the-logical-tree"></a><span data-ttu-id="8792e-105">元素和逻辑树</span><span class="sxs-lookup"><span data-stu-id="8792e-105">Elements and the Logical Tree</span></span>  
 <span data-ttu-id="8792e-106">在代码中创建 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的实例时，应该注意在调用类构造函数时所执行的代码中，需要有意地不包含 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的对象初始化的几个方面。</span><span class="sxs-lookup"><span data-stu-id="8792e-106">When you create an instance of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] class in code, you should be aware that several aspects of object initialization for a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] class are deliberately not a part of the code that is executed when calling the class constructor.</span></span> <span data-ttu-id="8792e-107">特别是对于控件类，该控件的大部分可视化表示形式都不是由构造函数定义的。</span><span class="sxs-lookup"><span data-stu-id="8792e-107">Particularly for a control class, most of the visual representation of that control is not defined by the constructor.</span></span> <span data-ttu-id="8792e-108">而是由控件的模板定义。</span><span class="sxs-lookup"><span data-stu-id="8792e-108">Instead, the visual representation is defined by the control's template.</span></span> <span data-ttu-id="8792e-109">模板可能来自各种源，但最常见的情况是来自于主题样式。</span><span class="sxs-lookup"><span data-stu-id="8792e-109">The template potentially comes from a variety of sources, but most often the template is obtained from theme styles.</span></span> <span data-ttu-id="8792e-110">模板实际上是晚期绑定的；在控件已准备好布局之后，才会将所需模板附加到相关控件。</span><span class="sxs-lookup"><span data-stu-id="8792e-110">Templates are effectively late-binding; the necessary template is not attached to the control in question until the control is ready for layout.</span></span> <span data-ttu-id="8792e-111">并且控件只有在已附加到连接到根级别的呈现图面的逻辑树时，才能准备好应用布局。</span><span class="sxs-lookup"><span data-stu-id="8792e-111">And the control is not ready for layout until it is attached to a logical tree that connects to a rendering surface at the root.</span></span> <span data-ttu-id="8792e-112">正是该根级别元素启动逻辑树中定义的所有子元素的呈现。</span><span class="sxs-lookup"><span data-stu-id="8792e-112">It is that root-level element that initiates the rendering of all of its child elements as defined in the logical tree.</span></span>  
  
 <span data-ttu-id="8792e-113">可视化树也参与此过程。</span><span class="sxs-lookup"><span data-stu-id="8792e-113">The visual tree also participates in this process.</span></span> <span data-ttu-id="8792e-114">通过模板成为可视化树一部分的元素也是在连接后才完全实例化的。</span><span class="sxs-lookup"><span data-stu-id="8792e-114">Elements that are part of the visual tree through the templates are also not fully instantiated until connected.</span></span>  
  
 <span data-ttu-id="8792e-115">此行为的结果是依赖某个元素已完成的可视化特征的某些操作需要额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="8792e-115">The consequences of this behavior are that certain operations that rely on the completed visual characteristics of an element require additional steps.</span></span> <span data-ttu-id="8792e-116">例如，如果你试图获取一个已构造但尚未附加到树中的类的可视化特征，就需要额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="8792e-116">An example is if you are attempting to get the visual characteristics of a class that was constructed but not yet attached to a tree.</span></span> <span data-ttu-id="8792e-117">例如，如果你想要调用<xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A>上<xref:System.Windows.Media.Imaging.RenderTargetBitmap>，通过传递时的视觉对象是未连接到树中，元素的其他初始化步骤在完成之前，该元素不是直观地完成。</span><span class="sxs-lookup"><span data-stu-id="8792e-117">For instance, if you want to call <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> on a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and the visual you are passing is an element not connected to a tree, that element is not visually complete until additional initialization steps are completed.</span></span>  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a><span data-ttu-id="8792e-118">使用 BeginInit 和 EndInit 初始化元素</span><span class="sxs-lookup"><span data-stu-id="8792e-118">Using BeginInit and EndInit to Initialize the Element</span></span>  
 <span data-ttu-id="8792e-119">中的各种类[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实现<xref:System.ComponentModel.ISupportInitialize>接口。</span><span class="sxs-lookup"><span data-stu-id="8792e-119">Various classes in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implement the <xref:System.ComponentModel.ISupportInitialize> interface.</span></span> <span data-ttu-id="8792e-120">你使用<xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>和<xref:System.ComponentModel.ISupportInitialize.EndInit%2A>接口来表示包含初始化步骤 （例如，设置属性值影响呈现的） 在代码中的一个区域的方法。</span><span class="sxs-lookup"><span data-stu-id="8792e-120">You use the <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> and <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> methods of the interface to denote a region in your code that contains initialization steps (such as setting property values that affect rendering).</span></span> <span data-ttu-id="8792e-121">后<xref:System.ComponentModel.ISupportInitialize.EndInit%2A>调用序列中，在布局系统可以处理元素并启动寻找隐式样式。</span><span class="sxs-lookup"><span data-stu-id="8792e-121">After <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> is called in the sequence, the layout system can process the element and start looking for an implicit style.</span></span>  
  
 <span data-ttu-id="8792e-122">如果该元素设置属性上是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>派生类，则可以调用的类版本<xref:System.Windows.FrameworkElement.BeginInit%2A>和<xref:System.Windows.FrameworkElement.EndInit%2A>而不是强制转换为<xref:System.ComponentModel.ISupportInitialize>。</span><span class="sxs-lookup"><span data-stu-id="8792e-122">If the element you are setting properties on is a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class, then you can call the class versions of <xref:System.Windows.FrameworkElement.BeginInit%2A> and <xref:System.Windows.FrameworkElement.EndInit%2A> rather than casting to <xref:System.ComponentModel.ISupportInitialize>.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="8792e-123">代码示例</span><span class="sxs-lookup"><span data-stu-id="8792e-123">Sample Code</span></span>  
 <span data-ttu-id="8792e-124">下面的示例是使用呈现一个控制台应用程序的示例代码[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]和<xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType>宽松[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件来说明的正确位置<xref:System.Windows.FrameworkElement.BeginInit%2A>和<xref:System.Windows.FrameworkElement.EndInit%2A>相对于其他[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]调用调整影响呈现的属性。</span><span class="sxs-lookup"><span data-stu-id="8792e-124">The following example is sample code for a console application that uses rendering [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] and <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> of a loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file to illustrate the proper placement of <xref:System.Windows.FrameworkElement.BeginInit%2A> and <xref:System.Windows.FrameworkElement.EndInit%2A> around other [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] calls that adjust properties that affect rendering.</span></span>  
  
 <span data-ttu-id="8792e-125">该示例仅演示主要函数。</span><span class="sxs-lookup"><span data-stu-id="8792e-125">The example illustrates the main function only.</span></span> <span data-ttu-id="8792e-126">函数 `Rasterize` 和 `Save`（未显示）是负责图像处理和 IO 的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="8792e-126">The functions `Rasterize` and `Save` (not shown) are utility functions that take care of image processing and IO.</span></span>  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a><span data-ttu-id="8792e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8792e-127">See Also</span></span>  
 [<span data-ttu-id="8792e-128">WPF 中的树</span><span class="sxs-lookup"><span data-stu-id="8792e-128">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="8792e-129">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="8792e-129">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="8792e-130">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="8792e-130">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
