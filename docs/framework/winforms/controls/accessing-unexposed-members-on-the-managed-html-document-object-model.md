---
title: 在托管 HTML 文档对象模型中访问未公开成员
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 20341a44eb8a43a9d130e0b76d23b513738c6782
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011888"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="fa08b-102">在托管 HTML 文档对象模型中访问未公开成员</span><span class="sxs-lookup"><span data-stu-id="fa08b-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="fa08b-103">托管 HTML 文档对象模型 (DOM) 包含一个名为类<xref:System.Windows.Forms.HtmlElement>公开属性、 方法和事件的所有 HTML 元素都有共同点。</span><span class="sxs-lookup"><span data-stu-id="fa08b-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="fa08b-104">有时，但是，你将需要访问托管的接口不会直接公开的成员。</span><span class="sxs-lookup"><span data-stu-id="fa08b-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="fa08b-105">本主题介绍两种方法可访问未公开的成员，包括[!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)]和网页中定义的 VBScript 函数。</span><span class="sxs-lookup"><span data-stu-id="fa08b-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="fa08b-106">通过托管接口访问未公开的成员</span><span class="sxs-lookup"><span data-stu-id="fa08b-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="fa08b-107"><xref:System.Windows.Forms.HtmlDocument> 和<xref:System.Windows.Forms.HtmlElement>提供四种方法来访问未公开成员。</span><span class="sxs-lookup"><span data-stu-id="fa08b-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="fa08b-108">下表显示类型和其相应的方法。</span><span class="sxs-lookup"><span data-stu-id="fa08b-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="fa08b-109">成员类型</span><span class="sxs-lookup"><span data-stu-id="fa08b-109">Member Type</span></span>|<span data-ttu-id="fa08b-110">方法</span><span class="sxs-lookup"><span data-stu-id="fa08b-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fa08b-111">属性 (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="fa08b-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="fa08b-112">方法</span><span class="sxs-lookup"><span data-stu-id="fa08b-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="fa08b-113">事件 (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="fa08b-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="fa08b-114">事件 (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="fa08b-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="fa08b-115">事件 (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="fa08b-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="fa08b-116">当使用这些方法时，假定您具有正确的基础类型的元素。</span><span class="sxs-lookup"><span data-stu-id="fa08b-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="fa08b-117">假设你想要收听`Submit`的事件`FORM`上对应的 HTML 元素页上，因此，你可以在执行一些预处理`FORM`的值之前用户将其提交到服务器。</span><span class="sxs-lookup"><span data-stu-id="fa08b-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="fa08b-118">理想情况下，如果你可以控制 HTML，您需要定义`FORM`具有一个唯一`ID`属性。</span><span class="sxs-lookup"><span data-stu-id="fa08b-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="fa08b-119">加载到此页后<xref:System.Windows.Forms.WebBrowser>控件，可以使用<xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>方法来检索`FORM`在运行的时使用`form1`作为自变量。</span><span class="sxs-lookup"><span data-stu-id="fa08b-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="fa08b-120">访问非托管的接口</span><span class="sxs-lookup"><span data-stu-id="fa08b-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="fa08b-121">此外可以通过使用由每个 DOM 类公开的非托管的组件对象模型 (COM) 接口访问托管 HTML DOM 上的未公开的成员。</span><span class="sxs-lookup"><span data-stu-id="fa08b-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="fa08b-122">如果需要进行多次调用未公开成员，或未公开的成员返回不使用托管 HTML DOM 的包装其他非托管的接口是建议这样做</span><span class="sxs-lookup"><span data-stu-id="fa08b-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="fa08b-123">下表显示了所有托管 HTML dom。 通过公开的非托管接口</span><span class="sxs-lookup"><span data-stu-id="fa08b-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="fa08b-124">单击每个链接的说明其用途和有关示例代码。</span><span class="sxs-lookup"><span data-stu-id="fa08b-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="fa08b-125">类型</span><span class="sxs-lookup"><span data-stu-id="fa08b-125">Type</span></span>|<span data-ttu-id="fa08b-126">非托管的接口</span><span class="sxs-lookup"><span data-stu-id="fa08b-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="fa08b-127">使用 COM 接口的最简单方法是添加到非托管 HTML DOM 库 (MSHTML.dll) 的引用从应用程序，虽然这是不受支持。</span><span class="sxs-lookup"><span data-stu-id="fa08b-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="fa08b-128">有关详细信息，请参阅[知识库文章 934368](https://support.microsoft.com/kb/934368)。</span><span class="sxs-lookup"><span data-stu-id="fa08b-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="fa08b-129">访问脚本函数</span><span class="sxs-lookup"><span data-stu-id="fa08b-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="fa08b-130">HTML 页可以定义一个或多个函数，通过使用一种脚本语言，如[!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)]或 VBScript。</span><span class="sxs-lookup"><span data-stu-id="fa08b-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="fa08b-131">这些函数的内部放置`SCRIPT`页在页中，并可对 DOM 按需或响应的事件中运行</span><span class="sxs-lookup"><span data-stu-id="fa08b-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="fa08b-132">可以调用任何脚本函数定义在 HTML 页使用<xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fa08b-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="fa08b-133">如果脚本方法返回一个 HTML 元素，您可以使用强制转换将转换到此返回结果<xref:System.Windows.Forms.HtmlElement>。</span><span class="sxs-lookup"><span data-stu-id="fa08b-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="fa08b-134">有关详细信息和代码示例，请参阅<xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>。</span><span class="sxs-lookup"><span data-stu-id="fa08b-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa08b-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa08b-135">See also</span></span>

- [<span data-ttu-id="fa08b-136">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="fa08b-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
