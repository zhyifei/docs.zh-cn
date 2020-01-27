---
title: 显示用于 ErrorProvider 组件的窗体验证的错误图标
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
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745907"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="5f57c-102">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="5f57c-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="5f57c-103">用户输入无效数据时，可以使用 Windows 窗体 <xref:System.Windows.Forms.ErrorProvider> 组件显示错误图标。</span><span class="sxs-lookup"><span data-stu-id="5f57c-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="5f57c-104">窗体上必须至少有两个控件，才能在它们之间进行 tab 键排列，从而调用验证代码。</span><span class="sxs-lookup"><span data-stu-id="5f57c-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="5f57c-105">当控件的值无效时显示错误图标</span><span class="sxs-lookup"><span data-stu-id="5f57c-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="5f57c-106">向 Windows 窗体添加两个控件（例如文本框）。</span><span class="sxs-lookup"><span data-stu-id="5f57c-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="5f57c-107">将 <xref:System.Windows.Forms.ErrorProvider> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="5f57c-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="5f57c-108">选择第一个控件并将代码添加到其 <xref:System.Windows.Forms.Control.Validating> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5f57c-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="5f57c-109">为了使此代码正常运行，该过程必须连接到事件。</span><span class="sxs-lookup"><span data-stu-id="5f57c-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="5f57c-110">有关详细信息，请参阅[如何：在运行时为 Windows 窗体创建事件处理程序](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="5f57c-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="5f57c-111">以下代码将测试用户输入的数据的有效性;如果数据无效，则调用 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="5f57c-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="5f57c-112"><xref:System.Windows.Forms.ErrorProvider.SetError%2A> 方法的第一个参数指定要在其旁边显示图标的控件。</span><span class="sxs-lookup"><span data-stu-id="5f57c-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="5f57c-113">第二个参数是要显示的错误文本。</span><span class="sxs-lookup"><span data-stu-id="5f57c-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="5f57c-114">（视觉C#对象、 C++视觉对象）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5f57c-114">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="5f57c-115">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f57c-115">Run the project.</span></span> <span data-ttu-id="5f57c-116">在第一个控件中键入无效（在此示例中为非数字）数据，然后按 tab 键。</span><span class="sxs-lookup"><span data-stu-id="5f57c-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="5f57c-117">显示错误图标时，用鼠标指针指向它，查看错误文本。</span><span class="sxs-lookup"><span data-stu-id="5f57c-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f57c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f57c-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="5f57c-119">ErrorProvider 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="5f57c-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="5f57c-120">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 세트에 있는 오류 보기</span><span class="sxs-lookup"><span data-stu-id="5f57c-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
