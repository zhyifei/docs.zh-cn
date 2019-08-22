---
title: 如何：设置 Windows 窗体控件显示的文本
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666157"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="a17e4-102">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="a17e4-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="a17e4-103">Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。</span><span class="sxs-lookup"><span data-stu-id="a17e4-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="a17e4-104">例如, <xref:System.Windows.Forms.Button>控件通常会显示一个标题, 指示在单击该按钮时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a17e4-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="a17e4-105">对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。</span><span class="sxs-lookup"><span data-stu-id="a17e4-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="a17e4-106">可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。</span><span class="sxs-lookup"><span data-stu-id="a17e4-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="a17e4-107">还可以使用[设计器](#designer)设置文本。</span><span class="sxs-lookup"><span data-stu-id="a17e4-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="a17e4-108">编程</span><span class="sxs-lookup"><span data-stu-id="a17e4-108">Programmatic</span></span>

1. <span data-ttu-id="a17e4-109">将 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为字符串。</span><span class="sxs-lookup"><span data-stu-id="a17e4-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="a17e4-110">若要创建带下划线的访问键, 请在将作为访问密钥的字母前包含一个 "与" 符号 (&)。</span><span class="sxs-lookup"><span data-stu-id="a17e4-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="a17e4-111">将 <xref:System.Windows.Forms.Control.Font%2A> 属性设置为类型 <xref:System.Drawing.Font> 的对象。</span><span class="sxs-lookup"><span data-stu-id="a17e4-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="a17e4-112">可使用转义符来显示用户界面元素中的特殊字符，通常对这些元素（如菜单项）有着不同的解释。</span><span class="sxs-lookup"><span data-stu-id="a17e4-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="a17e4-113">例如, 下面的代码行将菜单项的文本设置为 "现在为完全不同的内容 &":</span><span class="sxs-lookup"><span data-stu-id="a17e4-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="a17e4-114">Designer</span><span class="sxs-lookup"><span data-stu-id="a17e4-114">Designer</span></span>

1. <span data-ttu-id="a17e4-115">在 Visual Studio 的 "**属性**" 窗口中, 将控件的 " **Text** " 属性设置为相应的字符串。</span><span class="sxs-lookup"><span data-stu-id="a17e4-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="a17e4-116">若要创建带下划线的快捷键, 请在将作为快捷键的字母前包含 "and" 符 (&)。</span><span class="sxs-lookup"><span data-stu-id="a17e4-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="a17e4-117">在 "**属性**" 窗口中, 选择 "![**字体**" 属性旁边的省略号按钮 (省略号按钮 (...),](./media/visual-studio-ellipsis-button.png)位于 Visual Studio 属性窗口中)。</span><span class="sxs-lookup"><span data-stu-id="a17e4-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="a17e4-118">在 "标准字体" 对话框中, 选择所需的字体、字体样式、大小、效果 (如删除线或下划线) 和脚本。</span><span class="sxs-lookup"><span data-stu-id="a17e4-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="a17e4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a17e4-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a17e4-120">如何：为 Windows 窗体控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="a17e4-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="a17e4-121">如何：响应 Windows 窗体按钮单击</span><span class="sxs-lookup"><span data-stu-id="a17e4-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
