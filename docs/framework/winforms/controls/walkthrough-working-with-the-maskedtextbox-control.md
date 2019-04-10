---
title: 演练：使用 MaskedTextBox 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: ff9a0edb44a95f5853edf711e0a1559e3b2e3b15
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342440"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="7d72d-102">演练：使用 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="7d72d-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="7d72d-103">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="7d72d-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="7d72d-104">正在初始化<xref:System.Windows.Forms.MaskedTextBox>控件</span><span class="sxs-lookup"><span data-stu-id="7d72d-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="7d72d-105">使用<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>事件处理程序来提醒用户，当一个字符不符合掩码</span><span class="sxs-lookup"><span data-stu-id="7d72d-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="7d72d-106">分配到类型<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>属性并使用<xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>试图提交的值不是有效的类型时向用户发出警报的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="7d72d-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="7d72d-107">创建项目并添加控件</span><span class="sxs-lookup"><span data-stu-id="7d72d-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="7d72d-108">若要向窗体添加 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="7d72d-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="7d72d-109">打开想要放置该窗的体<xref:System.Windows.Forms.MaskedTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7d72d-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="7d72d-110">拖动<xref:System.Windows.Forms.MaskedTextBox>控件从**工具箱**向窗体。</span><span class="sxs-lookup"><span data-stu-id="7d72d-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="7d72d-111">右键单击该控件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="7d72d-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="7d72d-112">在中**属性**窗口中，选择**掩码**属性，单击 **...** （省略号） 按钮旁边的属性名称。</span><span class="sxs-lookup"><span data-stu-id="7d72d-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="7d72d-113">在中**输入掩码**对话框中，选择**短日期**掩码，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7d72d-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="7d72d-114">在中**属性**窗口中设置<xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="7d72d-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="7d72d-115">此属性会导致短的提示音，每次用户尝试输入不违反掩码定义的字符。</span><span class="sxs-lookup"><span data-stu-id="7d72d-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="7d72d-116">掩码属性支持的字符的摘要，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7d72d-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="7d72d-117">提醒用户输入错误</span><span class="sxs-lookup"><span data-stu-id="7d72d-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="7d72d-118">添加被拒绝的掩码输入的气球状提示</span><span class="sxs-lookup"><span data-stu-id="7d72d-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="7d72d-119">返回到**工具箱**并添加<xref:System.Windows.Forms.ToolTip>向窗体。</span><span class="sxs-lookup"><span data-stu-id="7d72d-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="7d72d-120">创建事件处理程序<xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>引发的事件<xref:System.Windows.Forms.ToolTip>发生的输入的错误。</span><span class="sxs-lookup"><span data-stu-id="7d72d-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="7d72d-121">气球状提示保持可见，五秒，或直到用户单击它。</span><span class="sxs-lookup"><span data-stu-id="7d72d-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="7d72d-122">不是有效的类型向用户发出警报</span><span class="sxs-lookup"><span data-stu-id="7d72d-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="7d72d-123">添加无效的数据类型的气球状提示</span><span class="sxs-lookup"><span data-stu-id="7d72d-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="7d72d-124">在窗体中<xref:System.Windows.Forms.Form.Load>事件处理程序分配<xref:System.Type>对象，表示<xref:System.DateTime>键入到<xref:System.Windows.Forms.MaskedTextBox>控件的<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>属性：</span><span class="sxs-lookup"><span data-stu-id="7d72d-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="7d72d-125">为 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件添加事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="7d72d-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d72d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d72d-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="7d72d-127">MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="7d72d-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
