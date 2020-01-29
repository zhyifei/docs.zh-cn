---
title: 在 Windows 窗体应用程序中创建 HTML 文档查看器
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732845"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>방법: Windows Forms 애플리케이션에서 HTML 문서 뷰어 만들기
您可以使用 <xref:System.Windows.Forms.WebBrowser> 控件来显示和打印 HTML 文档，而无需提供 Internet Web 浏览器的完整功能。 当你希望利用 HTML 的格式设置功能，但不希望你的用户加载可能包含不受信任的 Web 控件或可能是恶意脚本代码的任意网页时，这非常有用。 例如，你可能想要以这种方式限制 <xref:System.Windows.Forms.WebBrowser> 控件的功能，例如，将其用作 HTML 电子邮件查看器或在应用程序中提供 HTML 格式的帮助。  
  
### <a name="to-create-an-html-document-viewer"></a>创建 HTML 文档查看器  
  
1. 将 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 属性设置为 "`false`，以防止 <xref:System.Windows.Forms.WebBrowser> 控件打开拖放到它上面的文件。  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. 将 <xref:System.Windows.Forms.WebBrowser.Url%2A> 属性设置为要显示的初始文件的位置。  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- `webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤  
  
- `System` 및 `System.Windows.Forms` 어셈블리에 대한 참조  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser 컨트롤 개요](webbrowser-control-overview.md)
- [WebBrowser 보안](webbrowser-security.md)
- [방법: WebBrowser 컨트롤을 사용하여 URL 탐색](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [방법: WebBrowser 컨트롤을 사용하여 인쇄](how-to-print-with-a-webbrowser-control.md)
