---
title: 如何：在托管 HTML 文档对象模型中访问 HTML 源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 49a50bdf5ea0f24d712458c739b7829ee73d157a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527808"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>如何：在托管 HTML 文档对象模型中访问 HTML 源
<xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 控件中的 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 和 <xref:System.Windows.Forms.WebBrowser> 属性返回当前文档的 HTML，显示方式与第一次显示的一样。 但是，如果通过使用方法和属性调用（例如 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 和 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>）修改此页面，则在调用 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 和 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 时不会显示这些更改。 若要获得 DOM 的最新 HTML 源，必须调用 HTML 元素上的 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 属性。  
  
 以下过程显示了如何检索动态源并将其显示在单独的快捷菜单中。  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>使用 OuterHtml 属性检索动态源  
  
1.  创建新的 Windows 窗体应用程序。 首先创建一个<xref:System.Windows.Forms.Form>，并调用它`Form1`。  
  
2.  主机<xref:System.Windows.Forms.WebBrowser>控制在 Windows 窗体应用程序，并将其命名`WebBrowser1`。 有关详细信息，请参阅[如何： 将 Web 浏览器功能添加 Windows 窗体应用程序](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)。  
  
3.  创建第二个<xref:System.Windows.Forms.Form>调用应用程序中`CodeForm`。  
  
4.  添加<xref:System.Windows.Forms.RichTextBox>控制转移到`CodeForm`并设置其<xref:System.Windows.Forms.Control.Dock%2A>属性`Fill`。  
  
5.  创建一个公共属性上`CodeForm`调用`Code`。  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  添加<xref:System.Windows.Forms.Button>控件名为`Button1`到你<xref:System.Windows.Forms.Form>，并监视的<xref:System.Windows.Forms.Control.Click>事件。 有关监视事件的详细信息，请参阅[事件](../../../../docs/standard/events/index.md)。  
  
7.  将以下代码添加到 <xref:System.Windows.Forms.Control.Click> 事件处理程序中。  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>可靠编程  
 在尝试检索 <xref:System.Windows.Forms.WebBrowser.Document%2A> 之前，应总是先测试它的值。 如果当前页未完成加载，则 <xref:System.Windows.Forms.WebBrowser.Document%2A> 或它的一个或多个子对象可能无法初始化。  
  
## <a name="see-also"></a>请参阅  
 [使用托管 HTML 文档对象模型](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [WebBrowser 控件概述](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
