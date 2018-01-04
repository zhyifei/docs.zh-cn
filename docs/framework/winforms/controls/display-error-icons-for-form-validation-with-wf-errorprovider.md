---
title: "如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 738ca9670635f78e8cb04318b192127184766c3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="9aca5-102">如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标</span><span class="sxs-lookup"><span data-stu-id="9aca5-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="9aca5-103">你可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件以显示错误图标，当用户输入无效数据。</span><span class="sxs-lookup"><span data-stu-id="9aca5-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="9aca5-104">你必须具有它们之间切换，从而调用的验证代码以在窗体上的至少两个控件。</span><span class="sxs-lookup"><span data-stu-id="9aca5-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="9aca5-105">若要将控件的值无效时显示错误图标</span><span class="sxs-lookup"><span data-stu-id="9aca5-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="9aca5-106">添加两个控件 — 例如，文本框中，向 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="9aca5-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="9aca5-107">添加<xref:System.Windows.Forms.ErrorProvider>组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="9aca5-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="9aca5-108">选择第一个控件，然后将代码添加到其<xref:System.Windows.Forms.Control.Validating>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9aca5-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="9aca5-109">为了使此代码正确运行，该过程必须连接到该事件。</span><span class="sxs-lookup"><span data-stu-id="9aca5-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="9aca5-110">有关详细信息，请参阅[如何： 在运行时添加的 Windows 窗体创建事件处理程序](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9aca5-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="9aca5-111">下面的代码测试的用户输入; 数据的有效性如果数据是无效的<xref:System.Windows.Forms.ErrorProvider.SetError%2A>调用方法。</span><span class="sxs-lookup"><span data-stu-id="9aca5-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="9aca5-112">第一个参数<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法指定在哪个控件旁边显示图标。</span><span class="sxs-lookup"><span data-stu-id="9aca5-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="9aca5-113">第二个参数是要显示的错误文本。</span><span class="sxs-lookup"><span data-stu-id="9aca5-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="9aca5-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)][!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9aca5-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="9aca5-115">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="9aca5-115">Run the project.</span></span> <span data-ttu-id="9aca5-116">键入第一个控件，然后切换到第二个 （在此示例中，非数字） 无效的数据。</span><span class="sxs-lookup"><span data-stu-id="9aca5-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="9aca5-117">显示错误图标时, 点它与鼠标指针以查看错误文本。</span><span class="sxs-lookup"><span data-stu-id="9aca5-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aca5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aca5-118">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [<span data-ttu-id="9aca5-119">ErrorProvider 组件概述</span><span class="sxs-lookup"><span data-stu-id="9aca5-119">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="9aca5-120">如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误</span><span class="sxs-lookup"><span data-stu-id="9aca5-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
