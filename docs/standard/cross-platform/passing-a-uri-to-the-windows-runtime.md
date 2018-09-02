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
ms.openlocfilehash: 5805c2c16cd23a18a0fe5bb587a3c106b307092f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423353"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>向 Windows 运行时传递 URI
Windows 运行时方法只接受绝对 URI。 如果将一个相对 URI 传递给 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 方法，则将会引发 <xref:System.ArgumentException> 异常。 原因是： 当你使用[!INCLUDE[wrt](../../../includes/wrt-md.md)]在.NET Framework 代码中，<xref:Windows.Foundation.Uri?displayProperty=nameWithType>类显示为<xref:System.Uri?displayProperty=nameWithType>在 Intellisense 中。 <xref:System.Uri?displayProperty=nameWithType>类允许相对 Uri，但<xref:Windows.Foundation.Uri?displayProperty=nameWithType>类不。 这也适用于 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 组件中公开的方法。 如果组件公开接收 URI 的方法，则代码中的签名包含 <xref:System.Uri?displayProperty=nameWithType>。 但是，组件的用户，签名包含<xref:Windows.Foundation.Uri?displayProperty=nameWithType>。 传递给组件的 URI 必须是绝对 URI。  
  
 本主题演示了如何检测绝对 URI 以及如何在引用应用包中的资源时创建一个。  
  
## <a name="detecting-and-using-an-absolute-uri"></a>检测和使用绝对 URI  
 使用 <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> 属性确保在将 URI 传递给 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 之前，该 URI 是绝对的。 使用此属性比捕获和处理 <xref:System.ArgumentException> 异常更为有效。  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>将绝对 URI 用于应用包中的资源  
 如果想要为应用包包含的资源指定 URI，可以使用 `ms-appx` 或 `ms-appx-web` 方案来创建绝对 URI。  
  
 下面的示例演示如何设置[源](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx)属性[WebView](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx)控件和[源](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx)属性[映像](https://msdn.microsoft.com/library/windows/apps/br242752.aspx)控件在名为页，请使用 XAML 和代码的文件夹中包含的资源。  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 有关这些方案的详细信息，请参阅[URI 方案](https://msdn.microsoft.com/library/windows/apps/jj655406.aspx)Windows 开发人员中心中。  
  
## <a name="see-also"></a>请参阅  
 [.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
