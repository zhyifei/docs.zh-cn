---
title: 如何：在 Windows 窗体应用程序中创建 HTML 文档查看器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 0eecefd961aed5408e7d02769056dc551e604b02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214567"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>如何：在 Windows 窗体应用程序中创建 HTML 文档查看器
可以使用<xref:System.Windows.Forms.WebBrowser>控件来显示和打印 HTML 文档，而无需提供 Internet Web 浏览器的完整功能。 如果想要充分利用 HTML 格式设置功能，但不是希望让用户以加载可能包含不受信任的 Web 控件或潜在的恶意脚本代码的任意网页，这很有用。 你可能想要限制的功能<xref:System.Windows.Forms.WebBrowser>控制这种方式，例如，若要将其用作 HTML 电子邮件查看器，或以 HTML 格式在中提供帮助你的应用程序。  
  
### <a name="to-create-an-html-document-viewer"></a>若要创建 HTML 文档查看器  
  
1.  设置<xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>属性设置为`false`以免<xref:System.Windows.Forms.WebBrowser>打开文件放到它上面的控件。  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  设置<xref:System.Windows.Forms.WebBrowser.Url%2A>属性设置为要显示的初始文件的位置。  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。  
  
-   对 `System` 和 `System.Windows.Forms` 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser 控件概述](webbrowser-control-overview.md)
- [WebBrowser 安全](webbrowser-security.md)
- [如何：使用 WebBrowser 控件导航到 URL](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [如何：使用 WebBrowser 控件打印](how-to-print-with-a-webbrowser-control.md)
