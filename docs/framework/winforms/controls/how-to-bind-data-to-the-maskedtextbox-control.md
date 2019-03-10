---
title: 如何：将数据绑定到 MaskedTextBox 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: b03eff45b8494253918ae4462c29f50568c81569
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717461"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="93e88-102">如何：将数据绑定到 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="93e88-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="93e88-103">您可以将数据绑定到<xref:System.Windows.Forms.MaskedTextBox>控制就像可以连接到任何其他 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="93e88-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="93e88-104">但是，如果在数据库中数据的格式与掩码定义所需的格式不匹配，您将需要重新设置数据格式。</span><span class="sxs-lookup"><span data-stu-id="93e88-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="93e88-105">下面的过程演示如何执行此操作使用<xref:System.Windows.Forms.Binding.Format>并<xref:System.Windows.Forms.Binding.Parse>的事件<xref:System.Windows.Forms.Binding>类来显示单独的电话号码和电话扩展数据库字段为单一的可编辑字段。</span><span class="sxs-lookup"><span data-stu-id="93e88-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="93e88-106">下面的过程要求你有权访问安装了 Northwind 示例数据库的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="93e88-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="93e88-107">若要将数据绑定到 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="93e88-107">To bind data to a MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="93e88-108">创建新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="93e88-108">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="93e88-109">将两个<xref:System.Windows.Forms.TextBox>控件拖动到窗体; 它们命名`FirstName`和`LastName`。</span><span class="sxs-lookup"><span data-stu-id="93e88-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3.  <span data-ttu-id="93e88-110">拖动<xref:System.Windows.Forms.MaskedTextBox>拖动到窗体控件; 其命名为`PhoneMask`。</span><span class="sxs-lookup"><span data-stu-id="93e88-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4.  <span data-ttu-id="93e88-111">设置<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>的属性`PhoneMask`到`(000) 000-0000 x9999`。</span><span class="sxs-lookup"><span data-stu-id="93e88-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5.  <span data-ttu-id="93e88-112">添加以下命名空间导入到的窗体。</span><span class="sxs-lookup"><span data-stu-id="93e88-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  <span data-ttu-id="93e88-113">右键单击窗体，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="93e88-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="93e88-114">将此代码放置在窗体类中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="93e88-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7.  <span data-ttu-id="93e88-115">添加事件处理程序<xref:System.Windows.Forms.Binding.Format>并<xref:System.Windows.Forms.Binding.Parse>事件，以合并和拆分`PhoneNumber`并`Extension`绑定中的字段<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="93e88-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8.  <span data-ttu-id="93e88-116">添加两个<xref:System.Windows.Forms.Button>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="93e88-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="93e88-117">命名它们`previousButton`和`nextButton`。</span><span class="sxs-lookup"><span data-stu-id="93e88-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="93e88-118">双击要添加的每个按钮<xref:System.Windows.Forms.Control.Click>事件处理程序，并填写下面的代码示例中所示的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="93e88-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="93e88-119">运行示例。</span><span class="sxs-lookup"><span data-stu-id="93e88-119">Run the sample.</span></span> <span data-ttu-id="93e88-120">编辑数据，并使用**上一步**并**下一步**按钮以查看数据是否正确地保存到<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="93e88-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93e88-121">示例</span><span class="sxs-lookup"><span data-stu-id="93e88-121">Example</span></span>  
 <span data-ttu-id="93e88-122">下面的代码示例是列出完成前面的过程而产生的完整代码。</span><span class="sxs-lookup"><span data-stu-id="93e88-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93e88-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="93e88-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="93e88-124">创建视觉对象C#或 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="93e88-124">Create a Visual C# or Visual Basic project.</span></span>  
  
-   <span data-ttu-id="93e88-125">添加<xref:System.Windows.Forms.TextBox>和<xref:System.Windows.Forms.MaskedTextBox>控件添加到窗体，如前面的过程中所述。</span><span class="sxs-lookup"><span data-stu-id="93e88-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
-   <span data-ttu-id="93e88-126">打开项目的默认窗体源代码文件。</span><span class="sxs-lookup"><span data-stu-id="93e88-126">Open the source code file for the project's default form.</span></span>  
  
-   <span data-ttu-id="93e88-127">将以前的"代码"部分中列出的代码替换为此文件中的源代码。</span><span class="sxs-lookup"><span data-stu-id="93e88-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
-   <span data-ttu-id="93e88-128">编译该应用程序。</span><span class="sxs-lookup"><span data-stu-id="93e88-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e88-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="93e88-129">See also</span></span>
- [<span data-ttu-id="93e88-130">演练：使用 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="93e88-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
