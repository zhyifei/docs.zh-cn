---
title: "如何：使用 Windows 窗体 TextBox 控件创建密码文本框"
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
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fe8c3c6ac3c0f47f5e78aa7ff3242a0c69c7f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="58c25-102">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="58c25-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="58c25-103">密码框是一个 Windows 窗体的文本框显示占位符字符，在用户键入一个字符串时。</span><span class="sxs-lookup"><span data-stu-id="58c25-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="58c25-104">若要创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="58c25-104">To create a password text box</span></span>  
  
1.  <span data-ttu-id="58c25-105">设置<xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性<xref:System.Windows.Forms.TextBox>控件添加到特定的字符。</span><span class="sxs-lookup"><span data-stu-id="58c25-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="58c25-106"><xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性指定显示在文本框中的字符。</span><span class="sxs-lookup"><span data-stu-id="58c25-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="58c25-107">例如，如果你想在密码框中显示星号，指定 * 有关<xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="58c25-107">For example, if you want asterisks displayed in the password box, specify * for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="58c25-108">然后，无论用户在文本框中键入的字符，将显示一个星号。</span><span class="sxs-lookup"><span data-stu-id="58c25-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2.  <span data-ttu-id="58c25-109">（可选）设置<xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="58c25-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="58c25-110">属性用于确定可以在文本框中键入多少个字符。</span><span class="sxs-lookup"><span data-stu-id="58c25-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="58c25-111">如果超过了最大长度，系统会发出播放提示音且文本框不接受任何更多的字符。</span><span class="sxs-lookup"><span data-stu-id="58c25-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="58c25-112">请注意，你可能不希望这样做，因为密码的最大长度可能会利用黑客尝试猜测密码。</span><span class="sxs-lookup"><span data-stu-id="58c25-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="58c25-113">下面的代码示例演示如何初始化将接受最多 14 个字符长的字符串，并显示星号来替代字符串的文本框。</span><span class="sxs-lookup"><span data-stu-id="58c25-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="58c25-114">`InitializeMyControl`不会自动执行过程，必须调用它。</span><span class="sxs-lookup"><span data-stu-id="58c25-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="58c25-115">使用<xref:System.Windows.Forms.TextBox.PasswordChar%2A>上文本框中的属性可帮助确保其他人将无法确定用户的密码，如果它们观察用户输入。</span><span class="sxs-lookup"><span data-stu-id="58c25-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="58c25-116">此安全措施不涉及任何种类的存储或传输可能导致你的应用程序逻辑的密码。</span><span class="sxs-lookup"><span data-stu-id="58c25-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="58c25-117">因为输入的文本不以任何方式进行加密，你应将其像任何其他机密数据。</span><span class="sxs-lookup"><span data-stu-id="58c25-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="58c25-118">即使没有这种情况下出现，密码是仍被视为纯文本字符串 （除非您已实施了其他安全措施）。</span><span class="sxs-lookup"><span data-stu-id="58c25-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="58c25-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="58c25-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="58c25-120">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="58c25-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="58c25-121">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="58c25-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="58c25-122">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="58c25-122">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="58c25-123">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="58c25-123">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="58c25-124">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="58c25-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="58c25-125">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="58c25-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="58c25-126">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="58c25-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
