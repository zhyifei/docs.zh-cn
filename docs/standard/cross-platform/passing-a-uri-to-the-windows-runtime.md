---
title: 向 Windows 运行时传递 URI
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c489ec893ea335c8fafc904cf2a12162580ec266
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025434"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="25508-102">向 Windows 运行时传递 URI</span><span class="sxs-lookup"><span data-stu-id="25508-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="25508-103">Windows 运行时方法只接受绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="25508-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="25508-104">如果相对 URI 传递给 Windows 运行时方法，<xref:System.ArgumentException>引发异常。</span><span class="sxs-lookup"><span data-stu-id="25508-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="25508-105">原因是：当在.NET Framework 代码中，使用 Windows 运行时<xref:Windows.Foundation.Uri?displayProperty=nameWithType>类显示为<xref:System.Uri?displayProperty=nameWithType>在 Intellisense 中。</span><span class="sxs-lookup"><span data-stu-id="25508-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="25508-106"><xref:System.Uri?displayProperty=nameWithType>类允许相对 Uri，但<xref:Windows.Foundation.Uri?displayProperty=nameWithType>类不。</span><span class="sxs-lookup"><span data-stu-id="25508-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="25508-107">这也是为 Windows 运行时组件中公开的方法，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="25508-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="25508-108">如果组件公开接收 URI 的方法，则代码中的签名包含 <xref:System.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="25508-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="25508-109">但是，组件的用户，签名包含<xref:Windows.Foundation.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="25508-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="25508-110">传递给组件的 URI 必须是绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="25508-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="25508-111">本主题演示了如何检测绝对 URI 以及如何在引用应用包中的资源时创建一个。</span><span class="sxs-lookup"><span data-stu-id="25508-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="25508-112">检测和使用绝对 URI</span><span class="sxs-lookup"><span data-stu-id="25508-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="25508-113">使用<xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>属性以确保将其传递给 Windows 运行时之前是绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="25508-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="25508-114">使用此属性比捕获和处理 <xref:System.ArgumentException> 异常更为有效。</span><span class="sxs-lookup"><span data-stu-id="25508-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="25508-115">将绝对 URI 用于应用包中的资源</span><span class="sxs-lookup"><span data-stu-id="25508-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="25508-116">如果想要为应用包包含的资源指定 URI，可以使用 `ms-appx` 或 `ms-appx-web` 方案来创建绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="25508-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="25508-117">下面的示例演示如何设置<xref:Windows.UI.Xaml.Controls.WebView.Source%2A>属性<xref:Windows.UI.Xaml.Controls.WebView>控件并<xref:Windows.UI.Xaml.Controls.Image.Source%2A>属性<xref:Windows.UI.Xaml.Controls.Image>控制对资源包含在名为页，请使用 XAML 和代码的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="25508-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="25508-118">有关这些方案的详细信息，请参阅[URI 方案](/windows/uwp/app-resources/uri-schemes)Windows 开发人员中心中。</span><span class="sxs-lookup"><span data-stu-id="25508-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25508-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="25508-119">See also</span></span>

- [<span data-ttu-id="25508-120">.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况</span><span class="sxs-lookup"><span data-stu-id="25508-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
