---
title: 如何：使用 OpenFileDialog 组件打开文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 87e7640da76205341b9e95310314800ac9dbfe30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678806"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a><span data-ttu-id="c1d86-102">如何：使用 OpenFileDialog 组件打开文件</span><span class="sxs-lookup"><span data-stu-id="c1d86-102">How to: Open Files Using the OpenFileDialog Component</span></span>
<span data-ttu-id="c1d86-103"><xref:System.Windows.Forms.OpenFileDialog>组件让用户可以浏览其计算机或网络上的任何计算机的文件夹并选择一个或多个要打开的文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-103">The <xref:System.Windows.Forms.OpenFileDialog> component allows users to browse the folders of their computer or any computer on the network and select one or more files to open.</span></span> <span data-ttu-id="c1d86-104">对话框返回用户在对话框中所选的文件路径和名称。</span><span class="sxs-lookup"><span data-stu-id="c1d86-104">The dialog box returns the path and name of the file the user selected in the dialog box.</span></span>  
  
 <span data-ttu-id="c1d86-105">用户选定要打开的文件后，可以使用两种机制来打开文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-105">Once the user has selected the file to be opened, there are two approaches to the mechanism of opening the file.</span></span> <span data-ttu-id="c1d86-106">如果想要使用文件流，则可以创建的实例<xref:System.IO.StreamReader>类。</span><span class="sxs-lookup"><span data-stu-id="c1d86-106">If you prefer to work with file streams, you can create an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="c1d86-107">或者，可以使用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法打开所选的文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-107">Alternately, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the selected file.</span></span>  
  
 <span data-ttu-id="c1d86-108">下面的第一个示例涉及<xref:System.Security.Permissions.FileIOPermission>权限检查 （如在下面的"安全说明"中所述），但可以让您访问到的文件名。</span><span class="sxs-lookup"><span data-stu-id="c1d86-108">The first example below involves a <xref:System.Security.Permissions.FileIOPermission> permission check (as described in the "Security Note" below), but gives you access to the filename.</span></span> <span data-ttu-id="c1d86-109">你可以在本地计算机、Intranet 以及 Internet 区域中使用这种技术。</span><span class="sxs-lookup"><span data-stu-id="c1d86-109">You can use this technique from the Local Machine, Intranet, and Internet zones.</span></span> <span data-ttu-id="c1d86-110">第二种方法也能<xref:System.Security.Permissions.FileIOPermission>权限检查，但提供更好地适用于的 Intranet 或 Internet 区域中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1d86-110">The second method also does a <xref:System.Security.Permissions.FileIOPermission> permission check, but is better suited for applications in the Intranet or Internet zones.</span></span>  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a><span data-ttu-id="c1d86-111">使用 OpenFileDialog 组件以流形式打开文件</span><span class="sxs-lookup"><span data-stu-id="c1d86-111">To open a file as a stream using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="c1d86-112">显示“打开文件”对话框，并调用方法来打开用户选择的文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-112">Display the **Open File** dialog box and call a method to open the file selected by the user.</span></span>  
  
     <span data-ttu-id="c1d86-113">一种方法是使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法以显示打开文件对话框中，并使用的实例<xref:System.IO.StreamReader>类以打开该文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-113">One approach is to use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the Open File dialog box, and use an instance of the <xref:System.IO.StreamReader> class to open the file.</span></span>  
  
     <span data-ttu-id="c1d86-114">下面的示例使用<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序打开的实例<xref:System.Windows.Forms.OpenFileDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-114">The example below uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open an instance of the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="c1d86-115">当用户选定某个文件并单击“确定”时，将打开对话框中所选的文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-115">When a file is chosen and the user clicks **OK**, the file selected in the dialog box opens.</span></span> <span data-ttu-id="c1d86-116">在这种情况下，内容会显示在一个消息框中，用于说明已经读取文件流。</span><span class="sxs-lookup"><span data-stu-id="c1d86-116">In this case, the contents are displayed in a message box, just to show that the file stream has been read.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c1d86-117">获取或设置<xref:System.Windows.Forms.FileDialog.FileName%2A>属性，您的程序集需要的特权等级授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="c1d86-117">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c1d86-118">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="c1d86-118">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="c1d86-119">有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d86-119">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="c1d86-120">该示例假定窗体具有<xref:System.Windows.Forms.Button>控件和一个<xref:System.Windows.Forms.OpenFileDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-120">The example assumes your form has a <xref:System.Windows.Forms.Button> control and an <xref:System.Windows.Forms.OpenFileDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     <span data-ttu-id="c1d86-121">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c1d86-121">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c1d86-122">有关从文件流读取的详细信息，请参阅<xref:System.IO.FileStream.BeginRead%2A>和<xref:System.IO.FileStream.Read%2A>。</span><span class="sxs-lookup"><span data-stu-id="c1d86-122">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A> and <xref:System.IO.FileStream.Read%2A>.</span></span>  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a><span data-ttu-id="c1d86-123">使用 OpenFileDialog 组件以文件形式打开文件</span><span class="sxs-lookup"><span data-stu-id="c1d86-123">To open a file as a file using the OpenFileDialog component</span></span>  
  
1.  <span data-ttu-id="c1d86-124">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法来显示的对话框和<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法以打开该文件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-124">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open the file.</span></span>  
  
     <span data-ttu-id="c1d86-125"><xref:System.Windows.Forms.OpenFileDialog>组件的<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法返回 compose 文件的字节数。</span><span class="sxs-lookup"><span data-stu-id="c1d86-125">The <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method returns the bytes that compose the file.</span></span> <span data-ttu-id="c1d86-126">这些字节提供可从中读取的流。</span><span class="sxs-lookup"><span data-stu-id="c1d86-126">These bytes give you a stream to read from.</span></span> <span data-ttu-id="c1d86-127">在以下示例中， <xref:System.Windows.Forms.OpenFileDialog> "cursor"筛选器，从而允许用户只选择具有文件扩展名与实例化组件`.cur`。</span><span class="sxs-lookup"><span data-stu-id="c1d86-127">In the example below, an <xref:System.Windows.Forms.OpenFileDialog> component is instantiated with a "cursor" filter on it, allowing the user to choose only files with the file name extension`.cur`.</span></span> <span data-ttu-id="c1d86-128">选择 `.cur` 文件后，窗体的光标将设置为所选光标。</span><span class="sxs-lookup"><span data-stu-id="c1d86-128">If a`.cur` file is chosen, the form's cursor is set to the selected cursor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c1d86-129">若要调用<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>方法，您的程序集需要的特权等级授予通过<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="c1d86-129">To call the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c1d86-130">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="c1d86-130">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="c1d86-131">有关详细信息，请参阅[代码访问安全性基础知识](../../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d86-131">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
     <span data-ttu-id="c1d86-132">该示例假定窗体具有<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="c1d86-132">The example assumes your form has a <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     <span data-ttu-id="c1d86-133">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c1d86-133">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1d86-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1d86-134">See also</span></span>
- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="c1d86-135">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="c1d86-135">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
