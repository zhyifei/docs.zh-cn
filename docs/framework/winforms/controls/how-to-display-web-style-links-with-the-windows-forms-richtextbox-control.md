---
title: 用 RichTextBox 控件显示 Web 样式链接
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 78a07a250744018f121b03f2973b1661ed6bf764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745539"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接

Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件可以将 Web 链接显示为彩色和带下划线。 您可以编写代码，以在单击链接时打开显示链接文本中所指定网站的浏览器窗口。

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>使用 RichTextBox 控件链接到网页

1. 将 <xref:System.Windows.Forms.RichTextBox.Text%2A> 属性设置为包含有效 URL 的字符串（例如 "http://www.microsoft.com/"）。

2. 请确保 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 属性设置为 `true` （默认值）。

3. 创建 <xref:System.Diagnostics.Process> 对象的新全局实例。

4. 为向浏览器发送所需文本的 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 事件编写事件处理程序。

    在下面的示例中，<xref:System.Windows.Forms.RichTextBox.LinkClicked> 事件会打开 Internet Explorer 的一个实例，该实例指向 <xref:System.Windows.Forms.RichTextBox> 控件的 <xref:System.Windows.Forms.RichTextBox.Text%2A> 属性中指定的 URL。 此示例假设窗体具有 <xref:System.Windows.Forms.RichTextBox> 控件。

    > [!IMPORTANT]
    > 在调用 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 方法时，如果在部分信任上下文中运行代码，则会遇到 <xref:System.Security.SecurityException> 异常，因为权限不足。 有关详细信息，请参阅 [Code Access Security Basics](../../misc/code-access-security-basics.md)。

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    （视觉C++对象）您必须通过在窗体的构造函数中包含以下语句来初始化 `p`的进程：

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    （视觉C#对象、 C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    完成操作后，立即停止创建的过程非常重要。 参考以上所示的代码，停止此过程的代码可能如下所示：

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
