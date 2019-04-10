---
title: 如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接
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
ms.openlocfilehash: 1902557e5dbdcee3c1facc18b6f5c3037c266a8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148234"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="c20ac-102">如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接</span><span class="sxs-lookup"><span data-stu-id="c20ac-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="c20ac-103">Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件可以显示为彩色并有下划线的 Web 链接。</span><span class="sxs-lookup"><span data-stu-id="c20ac-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="c20ac-104">可以编写将打开浏览器窗口中显示时单击该链接时链接文本中指定的 Web 站点的代码。</span><span class="sxs-lookup"><span data-stu-id="c20ac-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="c20ac-105">若要链接到网页上使用 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="c20ac-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="c20ac-106">设置<xref:System.Windows.Forms.RichTextBox.Text%2A>属性设置为包含有效的 URL 的字符串 (例如，"http://www.microsoft.com/")。</span><span class="sxs-lookup"><span data-stu-id="c20ac-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="c20ac-107">请确保<xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>属性设置为`true`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="c20ac-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="c20ac-108">创建新的全局实例<xref:System.Diagnostics.Process>对象。</span><span class="sxs-lookup"><span data-stu-id="c20ac-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="c20ac-109">写入的事件处理程序<xref:System.Windows.Forms.RichTextBox.LinkClicked>发送所需的文本的浏览器的事件。</span><span class="sxs-lookup"><span data-stu-id="c20ac-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="c20ac-110">在以下示例中，<xref:System.Windows.Forms.RichTextBox.LinkClicked>事件将打开 Internet 浏览器中指定的 URL 来的实例<xref:System.Windows.Forms.RichTextBox.Text%2A>属性的<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="c20ac-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="c20ac-111">此示例假定窗体具有<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="c20ac-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c20ac-112">在调用<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>方法，将会遇到<xref:System.Security.SecurityException>如果因特权不足而部分信任上下文中运行代码的异常。</span><span class="sxs-lookup"><span data-stu-id="c20ac-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="c20ac-113">有关详细信息，请参阅[代码访问安全性基础知识](../../misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c20ac-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="c20ac-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])，则必须初始化过程`p`，您可以通过在你的窗体的构造函数中包含以下语句来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="c20ac-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="c20ac-115">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c20ac-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="c20ac-116">请务必立即停止已创建完成后使用它的进程。</span><span class="sxs-lookup"><span data-stu-id="c20ac-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="c20ac-117">上面介绍的代码中引用，您的代码以停止该进程可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="c20ac-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c20ac-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c20ac-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="c20ac-119">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="c20ac-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="c20ac-120">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="c20ac-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
