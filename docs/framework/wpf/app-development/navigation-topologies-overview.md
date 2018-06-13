---
title: 导航拓扑概述
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 8976ba7973e4f53022846b98c47d5613fd6ba158
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557545"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="90945-102">导航拓扑概述</span><span class="sxs-lookup"><span data-stu-id="90945-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a> <span data-ttu-id="90945-103">此概述提供的简介中的导航拓扑[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="90945-103">This overview provides an introduction to navigation topologies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="90945-104">三个常见导航拓扑及示例将在随后讨论。</span><span class="sxs-lookup"><span data-stu-id="90945-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90945-105">在阅读本主题之前, 应该熟悉的概念中的结构化导航[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]使用页函数。</span><span class="sxs-lookup"><span data-stu-id="90945-105">Before reading this topic, you should be familiar with the concept of structured navigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] using page functions.</span></span> <span data-ttu-id="90945-106">有关这两个这些主题的详细信息，请参阅[结构化导航概述](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="90945-106">For more information on both of these topics, see [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="90945-107">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="90945-107">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="90945-108">导航拓扑</span><span class="sxs-lookup"><span data-stu-id="90945-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
-   [<span data-ttu-id="90945-109">结构化导航拓扑</span><span class="sxs-lookup"><span data-stu-id="90945-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
-   [<span data-ttu-id="90945-110">在固定线性拓扑中导航</span><span class="sxs-lookup"><span data-stu-id="90945-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
-   [<span data-ttu-id="90945-111">在固定分层拓扑中动态导航</span><span class="sxs-lookup"><span data-stu-id="90945-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
-   [<span data-ttu-id="90945-112">在动态生成的拓扑中导航</span><span class="sxs-lookup"><span data-stu-id="90945-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a><span data-ttu-id="90945-113">导航拓扑</span><span class="sxs-lookup"><span data-stu-id="90945-113">Navigation Topologies</span></span>  
 <span data-ttu-id="90945-114">在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，导航通常由页 (<xref:System.Windows.Controls.Page>) 替换为超链接 (<xref:System.Windows.Documents.Hyperlink>)，导航至其他页面时单击。</span><span class="sxs-lookup"><span data-stu-id="90945-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="90945-115">导航到的页由[!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)](请参阅[WPF 中的包 Uri](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="90945-115">Pages that are navigated to are identified by [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="90945-116">请考虑以下简单示例，可以显示页，超链接和[!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="90945-116">Consider the following simple example that shows pages, hyperlinks, and [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="90945-117">这些页面在进行排列*导航拓扑*由其结构如何页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="90945-118">此特定导航拓扑适用于简单的应用场景，尽管导航可以要求更复杂的拓扑（其中的一些只能在应用程序运行时定义）。</span><span class="sxs-lookup"><span data-stu-id="90945-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="90945-119">本主题介绍三个常见导航拓扑：*固定线性*，*固定分层*，和*动态生成*。</span><span class="sxs-lookup"><span data-stu-id="90945-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="90945-120">通过具有的示例演示了每个导航拓扑[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]显示如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="90945-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 <span data-ttu-id="90945-121">![具有数据项的任务页](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")</span><span class="sxs-lookup"><span data-stu-id="90945-121">![Task pages with data items](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")</span></span>  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a><span data-ttu-id="90945-122">结构化导航拓扑</span><span class="sxs-lookup"><span data-stu-id="90945-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="90945-123">有两种广义类型的导航拓扑：</span><span class="sxs-lookup"><span data-stu-id="90945-123">There are two broad types of navigation topologies:</span></span>  
  
-   <span data-ttu-id="90945-124">**固定拓扑**：在编译时定义，在运行时不能更改。</span><span class="sxs-lookup"><span data-stu-id="90945-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="90945-125">按线性或层次顺序在固定序列的页面之间导航时，固定拓扑将很有用。</span><span class="sxs-lookup"><span data-stu-id="90945-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
-   <span data-ttu-id="90945-126">**动态拓扑**：在运行时基于从用户、应用程序或系统收集的输入进行定义。</span><span class="sxs-lookup"><span data-stu-id="90945-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="90945-127">当页面可以按不同序列进行导航时，动态拓扑将很有用。</span><span class="sxs-lookup"><span data-stu-id="90945-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="90945-128">虽然使用页可以创建导航拓扑，但是这些示例使用页函数，因为它们提供附加支持，从而通过拓扑页简化对传递和返回数据的支持。</span><span class="sxs-lookup"><span data-stu-id="90945-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="90945-129">在固定线性拓扑中导航</span><span class="sxs-lookup"><span data-stu-id="90945-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="90945-130">固定线性拓扑类似于向导的结构，即在固定序列中导航一个或多个向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="90945-131">下图显示具有固定线性拓扑的向导的高级结构和流。</span><span class="sxs-lookup"><span data-stu-id="90945-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology.</span></span>  
  
 <span data-ttu-id="90945-132">![导航拓扑关系图](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")</span><span class="sxs-lookup"><span data-stu-id="90945-132">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")</span></span>  
  
 <span data-ttu-id="90945-133">在固定线性拓扑中导航的典型行为包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="90945-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
-   <span data-ttu-id="90945-134">从调用页导航到启动程序页，启动程序页初始化向导并导航到第一个向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="90945-135">启动程序页 ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-较少<xref:System.Windows.Navigation.PageFunction%601>) 不是必需的因为调用页可以直接调用的第一向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="90945-136">但是，使用启动程序页可以简化向导初始化，特别是初始化较复杂时。</span><span class="sxs-lookup"><span data-stu-id="90945-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="90945-137">用户可以使用“后退”和“前进”按钮（或超链接）在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="90945-138">用户可以使用日志在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-138">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="90945-139">用户可以通过按下“取消”按钮从任何向导页取消向导。</span><span class="sxs-lookup"><span data-stu-id="90945-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="90945-140">用户可以在最后一个向导页上通过按下“完成”按钮来接受向导。</span><span class="sxs-lookup"><span data-stu-id="90945-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="90945-141">如果向导已取消，该向导会返回相应结果，但不返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="90945-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="90945-142">如果用户接受向导，该向导会返回相应结果并返回所收集的数据。</span><span class="sxs-lookup"><span data-stu-id="90945-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="90945-143">向导完成（接受或取消）后，向导所包含的页便会从日志中删除。</span><span class="sxs-lookup"><span data-stu-id="90945-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="90945-144">这使得每个向导实例都保持独立，从而避免潜在的数据反常或状态异常。</span><span class="sxs-lookup"><span data-stu-id="90945-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="90945-145">在固定分层拓扑中动态导航</span><span class="sxs-lookup"><span data-stu-id="90945-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="90945-146">在某些应用程序中，页允许导航到两个或更多其他页，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="90945-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="90945-147">![一个可以导航到多个页的页面](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")</span><span class="sxs-lookup"><span data-stu-id="90945-147">![A page that can navigate to multiple pages](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")</span></span>  
  
 <span data-ttu-id="90945-148">此结构称为固定分层拓扑，分层的遍历序列通常在运行时由应用程序或用户确定。</span><span class="sxs-lookup"><span data-stu-id="90945-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="90945-149">运行时，对于允许导航到两个或更多其他页的分层中的每个页面，会收集确定导航到的页所需的数据。</span><span class="sxs-lookup"><span data-stu-id="90945-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="90945-150">下图基于上图说明了其中一种可能的导航序列。</span><span class="sxs-lookup"><span data-stu-id="90945-150">The following figure illustrates one of several possible navigation sequences based on the previous figure.</span></span>  
  
 <span data-ttu-id="90945-151">![导航拓扑关系图](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")</span><span class="sxs-lookup"><span data-stu-id="90945-151">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")</span></span>  
  
 <span data-ttu-id="90945-152">即使固定分层结构中的页导航序列在运行时确定，用户体验仍会与固定线性拓扑的用户体验相同：</span><span class="sxs-lookup"><span data-stu-id="90945-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
-   <span data-ttu-id="90945-153">从调用页导航到启动程序页，启动程序页初始化向导并导航到第一个向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="90945-154">启动程序页 ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-较少<xref:System.Windows.Navigation.PageFunction%601>) 不是必需的因为调用页可以直接调用的第一向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="90945-155">但是，使用启动程序页可以简化向导初始化，特别是初始化较复杂时。</span><span class="sxs-lookup"><span data-stu-id="90945-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="90945-156">用户可以使用“后退”和“前进”按钮（或超链接）在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="90945-157">用户可以使用日志在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-157">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="90945-158">如果用户通过日志向后导航，他们可以更改导航序列。</span><span class="sxs-lookup"><span data-stu-id="90945-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
-   <span data-ttu-id="90945-159">用户可以通过按下“取消”按钮从任何向导页取消向导。</span><span class="sxs-lookup"><span data-stu-id="90945-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="90945-160">用户可以在最后一个向导页上通过按下“完成”按钮来接受向导。</span><span class="sxs-lookup"><span data-stu-id="90945-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="90945-161">如果向导已取消，该向导会返回相应结果，但不返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="90945-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="90945-162">如果用户接受向导，该向导会返回相应结果并返回所收集的数据。</span><span class="sxs-lookup"><span data-stu-id="90945-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="90945-163">向导完成（接受或取消）后，向导所包含的页便会从日志中删除。</span><span class="sxs-lookup"><span data-stu-id="90945-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="90945-164">这使得每个向导实例都保持独立，从而避免潜在的数据反常或状态异常。</span><span class="sxs-lookup"><span data-stu-id="90945-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="90945-165">在动态生成的拓扑中导航</span><span class="sxs-lookup"><span data-stu-id="90945-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="90945-166">在某些应用程序中，两个或更多页的导航序列只能在运行时由用户、应用程序或外部数据确定。</span><span class="sxs-lookup"><span data-stu-id="90945-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="90945-167">下图说明了一组导航序列未定的页面。</span><span class="sxs-lookup"><span data-stu-id="90945-167">The following figure illustrates a set of pages with an undetermined navigation sequence.</span></span>  
  
 <span data-ttu-id="90945-168">![导航拓扑关系图](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")</span><span class="sxs-lookup"><span data-stu-id="90945-168">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")</span></span>  
  
 <span data-ttu-id="90945-169">下图说明了在运行时用户所选的导航序列。</span><span class="sxs-lookup"><span data-stu-id="90945-169">The next figure illustrates a navigation sequence that was chosen by the user at run time.</span></span>  
  
 <span data-ttu-id="90945-170">![导航关系图](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")</span><span class="sxs-lookup"><span data-stu-id="90945-170">![Navigation diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")</span></span>  
  
 <span data-ttu-id="90945-171">该导航序列称为动态生成的拓扑。</span><span class="sxs-lookup"><span data-stu-id="90945-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="90945-172">对于用户而言，与其他导航拓扑一样，用户体验与以前拓扑的用户体验相同：</span><span class="sxs-lookup"><span data-stu-id="90945-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
-   <span data-ttu-id="90945-173">从调用页导航到启动程序页，启动程序页初始化向导并导航到第一个向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="90945-174">启动程序页 ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-较少<xref:System.Windows.Navigation.PageFunction%601>) 不是必需的因为调用页可以直接调用的第一向导页。</span><span class="sxs-lookup"><span data-stu-id="90945-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="90945-175">但是，使用启动程序页可以简化向导初始化，特别是初始化较复杂时。</span><span class="sxs-lookup"><span data-stu-id="90945-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="90945-176">用户可以使用“后退”和“前进”按钮（或超链接）在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="90945-177">用户可以使用日志在不同的页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="90945-177">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="90945-178">用户可以通过按下“取消”按钮从任何向导页取消向导。</span><span class="sxs-lookup"><span data-stu-id="90945-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="90945-179">用户可以在最后一个向导页上通过按下“完成”按钮来接受向导。</span><span class="sxs-lookup"><span data-stu-id="90945-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="90945-180">如果向导已取消，该向导会返回相应结果，但不返回任何数据。</span><span class="sxs-lookup"><span data-stu-id="90945-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="90945-181">如果用户接受向导，该向导会返回相应结果并返回所收集的数据。</span><span class="sxs-lookup"><span data-stu-id="90945-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="90945-182">向导完成（接受或取消）后，向导所包含的页便会从日志中删除。</span><span class="sxs-lookup"><span data-stu-id="90945-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="90945-183">这使得每个向导实例都保持独立，从而避免潜在的数据反常或状态异常。</span><span class="sxs-lookup"><span data-stu-id="90945-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90945-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="90945-184">See Also</span></span>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.PageFunction%601>  
 <xref:System.Windows.Navigation.NavigationService>  
 [<span data-ttu-id="90945-185">结构化导航概述</span><span class="sxs-lookup"><span data-stu-id="90945-185">Structured Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)
