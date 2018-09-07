---
title: 使用 UI 自动化访问嵌入式对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 05f9359aa055019b517abb1b7c86ca386d630e41
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080135"
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="b21c7-102">使用 UI 自动化访问嵌入式对象</span><span class="sxs-lookup"><span data-stu-id="b21c7-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="b21c7-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="b21c7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b21c7-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="b21c7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b21c7-105">本主题显示可如何使用 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 来公开嵌入在文本控件内容中的对象。</span><span class="sxs-lookup"><span data-stu-id="b21c7-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b21c7-106">嵌入对象可以包括图像、超链接、按钮、表或 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="b21c7-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="b21c7-107">嵌入对象可视为 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 文本提供程序的子项。</span><span class="sxs-lookup"><span data-stu-id="b21c7-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="b21c7-108">将能够通过与所有其他 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 元素相同的 UI 自动化树结构来公开嵌入对象。</span><span class="sxs-lookup"><span data-stu-id="b21c7-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="b21c7-109">而功能是通过嵌入对象控件类型通常需要的控件模式公开的（例如，由于超链接基于文本，因此超链接将支持 <xref:System.Windows.Automation.TextPattern>）。</span><span class="sxs-lookup"><span data-stu-id="b21c7-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="b21c7-110">![文本容器中的嵌入的对象。](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="b21c7-110">![Embedded objects in a text container.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="b21c7-111">示例文档包含文本内容 （"您知道吗？"...）和两个嵌入的对象 （一幅鲸鱼照片和一个文本超链接） 的代码示例使用作为目标。</span><span class="sxs-lookup"><span data-stu-id="b21c7-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b21c7-112">示例</span><span class="sxs-lookup"><span data-stu-id="b21c7-112">Example</span></span>  
 <span data-ttu-id="b21c7-113">下面的代码示例演示如何从 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 文本提供程序内检索嵌入对象的集合。</span><span class="sxs-lookup"><span data-stu-id="b21c7-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="b21c7-114">对于简介中提供的示例文档，将返回两个对象（一个图像元素和一个文本元素）。</span><span class="sxs-lookup"><span data-stu-id="b21c7-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b21c7-115">图像元素应具有一些与图像关联的内部文本来描述图像，这些文本通常位于图像的 <xref:System.Windows.Automation.AutomationElement.NameProperty> 中（例如，“蓝鲸”）。</span><span class="sxs-lookup"><span data-stu-id="b21c7-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="b21c7-116">但是，如果获得了跨越图像对象的文本范围，文本流中既不会返回图像，也不会返回此描述性文本。</span><span class="sxs-lookup"><span data-stu-id="b21c7-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="b21c7-117">示例</span><span class="sxs-lookup"><span data-stu-id="b21c7-117">Example</span></span>  
 <span data-ttu-id="b21c7-118">下面的代码示例演示如何从 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 文本提供程序内的嵌入对象中获取文本范围。</span><span class="sxs-lookup"><span data-stu-id="b21c7-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="b21c7-119">检索的文本范围是一个空范围，</span><span class="sxs-lookup"><span data-stu-id="b21c7-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="b21c7-120">其中起始端点紧跟在“… ocean.”后的空格之后，结束端点位于表示嵌入超链接的结束“.”之前（如简介中提供的图像所示）。</span><span class="sxs-lookup"><span data-stu-id="b21c7-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="b21c7-121">即使这是一个空范围，也不会被视作退化的范围，因为它有非零跨度。</span><span class="sxs-lookup"><span data-stu-id="b21c7-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b21c7-122"><xref:System.Windows.Automation.TextPattern> 可以检索基于文本的嵌入对象（如超链接）；但是，将需要从嵌入对象中获取第二个 <xref:System.Windows.Automation.TextPattern> 才能公开其完整功能。</span><span class="sxs-lookup"><span data-stu-id="b21c7-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="b21c7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b21c7-123">See Also</span></span>  
 [<span data-ttu-id="b21c7-124">UI 自动化 TextPattern 概述</span><span class="sxs-lookup"><span data-stu-id="b21c7-124">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="b21c7-125">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="b21c7-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="b21c7-126">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="b21c7-126">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="b21c7-127">使用 UI 自动化向文本框添加内容</span><span class="sxs-lookup"><span data-stu-id="b21c7-127">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="b21c7-128">使用 UI 自动化查找和突出显示文本</span><span class="sxs-lookup"><span data-stu-id="b21c7-128">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
