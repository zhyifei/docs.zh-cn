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
ms.openlocfilehash: bd813d479cd4dfb61a08d9a8c4a4e7612084e878
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532602"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="bd840-102">如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接</span><span class="sxs-lookup"><span data-stu-id="bd840-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="bd840-103">Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件可以显示为彩色和带下划线的 Web 链接。</span><span class="sxs-lookup"><span data-stu-id="bd840-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="bd840-104">你可以编写将打开一个显示时单击链接在链接文本中指定的网站的浏览器窗口的代码。</span><span class="sxs-lookup"><span data-stu-id="bd840-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="bd840-105">若要链接到网页上用 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="bd840-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="bd840-106">设置<xref:System.Windows.Forms.RichTextBox.Text%2A>属性为字符串，其中包含有效的 URL (例如，"http://www.microsoft.com/")。</span><span class="sxs-lookup"><span data-stu-id="bd840-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="bd840-107">请确保<xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>属性设置为`true`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="bd840-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="bd840-108">创建新的全局实例<xref:System.Diagnostics.Process>对象。</span><span class="sxs-lookup"><span data-stu-id="bd840-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="bd840-109">写入的事件处理程序<xref:System.Windows.Forms.RichTextBox.LinkClicked>发送所需的文本的浏览器的事件。</span><span class="sxs-lookup"><span data-stu-id="bd840-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="bd840-110">在示例中，<xref:System.Windows.Forms.RichTextBox.LinkClicked>事件将打开到中指定的 URL 的 Internet Explorer 实例<xref:System.Windows.Forms.RichTextBox.Text%2A>属性<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="bd840-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="bd840-111">此示例假定的窗体具有<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="bd840-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bd840-112">在调用<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>方法，将会遇到<xref:System.Security.SecurityException>异常如果由于没有足够的特权在部分信任的上下文中运行代码。</span><span class="sxs-lookup"><span data-stu-id="bd840-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="bd840-113">有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="bd840-113">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="bd840-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 必须初始化过程`p`，则你可以通过在你的窗体的构造函数中包括以下语句：</span><span class="sxs-lookup"><span data-stu-id="bd840-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="bd840-115">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="bd840-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="bd840-116">请务必立即停止你已创建完成后使用独立存储的过程。</span><span class="sxs-lookup"><span data-stu-id="bd840-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="bd840-117">上面显示的代码中引用，你的代码以停止进程可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd840-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd840-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd840-118">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="bd840-119">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="bd840-119">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="bd840-120">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="bd840-120">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
