---
title: 如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 39dd77fee36b172f6c38746bfe970094ec9edb4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223545"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="5cec8-102">如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标</span><span class="sxs-lookup"><span data-stu-id="5cec8-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="5cec8-103">可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件，用户输入无效数据时显示错误图标。</span><span class="sxs-lookup"><span data-stu-id="5cec8-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="5cec8-104">您必须具有至少两个选项卡上，它们之间并由此调用验证代码以窗体控件。</span><span class="sxs-lookup"><span data-stu-id="5cec8-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="5cec8-105">若要在控件的值无效时显示错误图标</span><span class="sxs-lookup"><span data-stu-id="5cec8-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="5cec8-106">添加两个控件 — 例如，文本框中，向 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="5cec8-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="5cec8-107">添加<xref:System.Windows.Forms.ErrorProvider>组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="5cec8-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="5cec8-108">选择第一个控件，然后将代码添加到其<xref:System.Windows.Forms.Control.Validating>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5cec8-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="5cec8-109">为了使此代码正常运行，该过程必须连接到该事件。</span><span class="sxs-lookup"><span data-stu-id="5cec8-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="5cec8-110">有关详细信息，请参阅[如何：在运行时为 Windows 窗体创建事件处理程序](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="5cec8-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="5cec8-111">下面的代码测试用户输入; 这些数据的有效性如果数据是无效的<xref:System.Windows.Forms.ErrorProvider.SetError%2A>调用方法。</span><span class="sxs-lookup"><span data-stu-id="5cec8-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="5cec8-112">第一个参数<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法指定用于控制为旁边显示图标。</span><span class="sxs-lookup"><span data-stu-id="5cec8-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="5cec8-113">第二个参数是要显示的错误文本。</span><span class="sxs-lookup"><span data-stu-id="5cec8-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="5cec8-114">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5cec8-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="5cec8-115">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="5cec8-115">Run the project.</span></span> <span data-ttu-id="5cec8-116">在第一个控件，然后第二个选项卡中键入无效 （在此示例中，非数字） 的数据。</span><span class="sxs-lookup"><span data-stu-id="5cec8-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="5cec8-117">当显示错误图标时，指向它使用鼠标指针以查看错误文本。</span><span class="sxs-lookup"><span data-stu-id="5cec8-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cec8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cec8-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="5cec8-119">ErrorProvider 组件概述</span><span class="sxs-lookup"><span data-stu-id="5cec8-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="5cec8-120">如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误</span><span class="sxs-lookup"><span data-stu-id="5cec8-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
