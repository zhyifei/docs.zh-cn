---
title: "如何：在字符串中放置引号（Windows 窗体）"
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
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a4141a27a3b195dbb747a827d2bd9426a948f83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="43bd1-102">如何：在字符串中放置引号（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="43bd1-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="43bd1-103">有时可能需要将引号（“”）放入文本字符串中。</span><span class="sxs-lookup"><span data-stu-id="43bd1-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="43bd1-104">例如：</span><span class="sxs-lookup"><span data-stu-id="43bd1-104">For example:</span></span>  
  
 <span data-ttu-id="43bd1-105">她说：“该好好款待你了！”</span><span class="sxs-lookup"><span data-stu-id="43bd1-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="43bd1-106">作为替代方法，你可以使用<xref:Microsoft.VisualBasic.ControlChars.Quote>字段为常数。</span><span class="sxs-lookup"><span data-stu-id="43bd1-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="43bd1-107">在代码中的字符串内放置引号</span><span class="sxs-lookup"><span data-stu-id="43bd1-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="43bd1-108">在 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 中，将两个引号插入一行中作为嵌入引号。</span><span class="sxs-lookup"><span data-stu-id="43bd1-108">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="43bd1-109">在 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 和 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] 中，插入转义序列 \\" 作为嵌入引号。</span><span class="sxs-lookup"><span data-stu-id="43bd1-109">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="43bd1-110">例如，若要创建前面提到的字符串，请使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="43bd1-110">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="43bd1-111">- 或 -</span><span class="sxs-lookup"><span data-stu-id="43bd1-111">-or-</span></span>  
  
2.  <span data-ttu-id="43bd1-112">插入 ASCII 字符或 Unicode 字符表示引号。</span><span class="sxs-lookup"><span data-stu-id="43bd1-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="43bd1-113">在 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 中，使用 ASCII 字符 (34)。</span><span class="sxs-lookup"><span data-stu-id="43bd1-113">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], use the ASCII character (34).</span></span> <span data-ttu-id="43bd1-114">在 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 中，使用 Unicode 字符 (\u0022)。</span><span class="sxs-lookup"><span data-stu-id="43bd1-114">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="43bd1-115">在本示例中，不能使用 \u0022，因为不能使用指定基本字符集中字符的通用字符名。</span><span class="sxs-lookup"><span data-stu-id="43bd1-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="43bd1-116">否则，将产生 C3851。</span><span class="sxs-lookup"><span data-stu-id="43bd1-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="43bd1-117">有关详细信息，请参阅[编译器错误 C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851)。</span><span class="sxs-lookup"><span data-stu-id="43bd1-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="43bd1-118">- 或 -</span><span class="sxs-lookup"><span data-stu-id="43bd1-118">-or-</span></span>  
  
3.  <span data-ttu-id="43bd1-119">还可以为该字符定义一个常数，然后在需要时使用。</span><span class="sxs-lookup"><span data-stu-id="43bd1-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43bd1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43bd1-120">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [<span data-ttu-id="43bd1-121">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="43bd1-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="43bd1-122">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="43bd1-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="43bd1-123">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="43bd1-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="43bd1-124">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="43bd1-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="43bd1-125">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="43bd1-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="43bd1-126">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="43bd1-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="43bd1-127">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="43bd1-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
