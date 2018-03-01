---
title: "如何：使用 WebBrowser 控件定位到 URL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a447d69eb6dafbff75ddd9d161abd4f78c607cdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="8c7ad-102">如何：使用 WebBrowser 控件定位到 URL</span><span class="sxs-lookup"><span data-stu-id="8c7ad-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="8c7ad-103">下面的代码示例演示如何导航<xref:System.Windows.Forms.WebBrowser>控件添加到特定的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c7ad-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="8c7ad-104">若要确定完全加载新文档时，处理<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="8c7ad-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="8c7ad-105">此事件的演示，请参阅[如何： 使用 WebBrowser 控件打印](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8c7ad-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c7ad-106">示例</span><span class="sxs-lookup"><span data-stu-id="8c7ad-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c7ad-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="8c7ad-107">Compiling the Code</span></span>  
 <span data-ttu-id="8c7ad-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8c7ad-108">This example requires:</span></span>  
  
-   <span data-ttu-id="8c7ad-109">名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。</span><span class="sxs-lookup"><span data-stu-id="8c7ad-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="8c7ad-110">对 `System` 和 `System.Windows.Forms` 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8c7ad-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7ad-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c7ad-111">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [<span data-ttu-id="8c7ad-112">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="8c7ad-112">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [<span data-ttu-id="8c7ad-113">如何：使用 WebBrowser 控件进行打印</span><span class="sxs-lookup"><span data-stu-id="8c7ad-113">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
