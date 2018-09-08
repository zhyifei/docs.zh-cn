---
title: 使用托管 HTML 文档对象模型
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 7800311895d1c0fac43577076226a68712164f60
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200046"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="d1efd-102">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="d1efd-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="d1efd-103">托管的 HTML 文档对象模型 (DOM) 提供包装器基于[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]HTML 类公开的 Internet 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="d1efd-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="d1efd-104">这些类用于处理 HTML 页面中承载<xref:System.Windows.Forms.WebBrowser>控件，或要生成新的页从一开始。</span><span class="sxs-lookup"><span data-stu-id="d1efd-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1efd-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="d1efd-105">In This Section</span></span>  
 [<span data-ttu-id="d1efd-106">如何：访问托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="d1efd-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="d1efd-107">介绍如何获取有效的实例<xref:System.Windows.Forms.HtmlDocument>从 Windows 窗体应用程序或<xref:System.Windows.Forms.UserControl>Internet Explorer 中承载。</span><span class="sxs-lookup"><span data-stu-id="d1efd-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="d1efd-108">如何：在托管 HTML 文档对象模型中访问 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="d1efd-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="d1efd-109">介绍如何获取原始的未修改 HTML 源，以及如何获取反映 DOM 的当前状态的"实时"源</span><span class="sxs-lookup"><span data-stu-id="d1efd-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="d1efd-110">如何：在托管 HTML 文档对象模型中更改元素的样式</span><span class="sxs-lookup"><span data-stu-id="d1efd-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="d1efd-111">介绍如何操作样式，将用来控制元素的可视显示它们。</span><span class="sxs-lookup"><span data-stu-id="d1efd-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="d1efd-112">在托管 HTML 文档对象模型中访问框架</span><span class="sxs-lookup"><span data-stu-id="d1efd-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="d1efd-113">描述什么是框架和框架集以及如何访问框架的 DOM。</span><span class="sxs-lookup"><span data-stu-id="d1efd-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="d1efd-114">在托管 HTML 文档对象模型中访问未公开的成员</span><span class="sxs-lookup"><span data-stu-id="d1efd-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="d1efd-115">介绍如何访问的基础 DOM 不具有的托管的等效项的成员。</span><span class="sxs-lookup"><span data-stu-id="d1efd-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d1efd-116">参考</span><span class="sxs-lookup"><span data-stu-id="d1efd-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="d1efd-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="d1efd-117">Related Sections</span></span>  
 [<span data-ttu-id="d1efd-118">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="d1efd-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1efd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1efd-119">See Also</span></span>  
 [<span data-ttu-id="d1efd-120">关于 DHTML 对象模型</span><span class="sxs-lookup"><span data-stu-id="d1efd-120">About the DHTML Object Model</span></span>](https://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
