---
title: 如何：使用 Windows 窗体 TextBox 控件创建密码文本框
ms.date: 03/30/2017
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
ms.openlocfilehash: 56391777c75db288c33d1b2192355be0df50f7ee
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046125"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="91972-102">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="91972-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="91972-103">密码框是一个 Windows 窗体文本框, 在用户键入字符串时显示占位符字符。</span><span class="sxs-lookup"><span data-stu-id="91972-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="91972-104">创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="91972-104">To create a password text box</span></span>

1. <span data-ttu-id="91972-105">将<xref:System.Windows.Forms.TextBox>控件<xref:System.Windows.Forms.TextBox.PasswordChar%2A>的属性设置为特定字符。</span><span class="sxs-lookup"><span data-stu-id="91972-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="91972-106"><xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性指定文本框中显示的字符。</span><span class="sxs-lookup"><span data-stu-id="91972-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="91972-107">例如, 如果希望在 "密码" 框中显示星号, 请在 "属性窗口<xref:System.Windows.Forms.TextBox.PasswordChar%2A>中为属性指定" \* "。</span><span class="sxs-lookup"><span data-stu-id="91972-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="91972-108">然后, 无论用户在文本框中键入什么字符, 都将显示一个星号。</span><span class="sxs-lookup"><span data-stu-id="91972-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="91972-109">可有可无<xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>设置属性。</span><span class="sxs-lookup"><span data-stu-id="91972-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="91972-110">属性确定在文本框中键入的字符数。</span><span class="sxs-lookup"><span data-stu-id="91972-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="91972-111">如果超过了最大长度, 系统会发出嘟嘟声, 文本框不接受任何其他字符。</span><span class="sxs-lookup"><span data-stu-id="91972-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="91972-112">请注意, 你可能不希望这样做, 因为密码的最大长度可能会被尝试猜测密码的黑客使用。</span><span class="sxs-lookup"><span data-stu-id="91972-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="91972-113">下面的代码示例演示如何初始化一个文本框, 该文本框将接受长度最长为14个字符的字符串, 并显示星号来替换字符串。</span><span class="sxs-lookup"><span data-stu-id="91972-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="91972-114">此`InitializeMyControl`过程不会自动执行; 必须调用它。</span><span class="sxs-lookup"><span data-stu-id="91972-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="91972-115">如果使用<xref:System.Windows.Forms.TextBox.PasswordChar%2A>文本框上的属性, 则可帮助确保其他人在观察用户输入密码时不能确定用户的密码。</span><span class="sxs-lookup"><span data-stu-id="91972-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="91972-116">此安全措施不包含任何类型的密码, 无论是由于应用程序逻辑造成的, 都不会出现任何类型的密码。</span><span class="sxs-lookup"><span data-stu-id="91972-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="91972-117">由于输入的文本未以任何方式进行加密, 因此应将其视为任何其他机密数据。</span><span class="sxs-lookup"><span data-stu-id="91972-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="91972-118">即使它不是这样, 也仍会将密码视为纯文本字符串 (除非您已经实现了一些附加的安全措施)。</span><span class="sxs-lookup"><span data-stu-id="91972-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="91972-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="91972-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="91972-120">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="91972-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="91972-121">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="91972-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="91972-122">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="91972-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="91972-123">如何：用引号将引号引起来</span><span class="sxs-lookup"><span data-stu-id="91972-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="91972-124">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="91972-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="91972-125">如何：在 "Windows 窗体 TextBox" 控件中查看多行</span><span class="sxs-lookup"><span data-stu-id="91972-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="91972-126">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="91972-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
