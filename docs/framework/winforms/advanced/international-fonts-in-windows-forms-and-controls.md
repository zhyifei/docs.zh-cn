---
title: Windows 窗体和控件中的国际字体
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208545"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="8378d-102">Windows 窗体和控件中的国际字体</span><span class="sxs-lookup"><span data-stu-id="8378d-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="8378d-103">国际应用程序中选择字体的推荐的方法是使用字体回退，只要有可能。</span><span class="sxs-lookup"><span data-stu-id="8378d-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="8378d-104">在系统确定哪一脚本字符的字体后备意味着属于。</span><span class="sxs-lookup"><span data-stu-id="8378d-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="8378d-105">使用字体回退</span><span class="sxs-lookup"><span data-stu-id="8378d-105">Using font fallback</span></span>

<span data-ttu-id="8378d-106">若要利用此功能，未设置<xref:System.Drawing.Font>为你的窗体或任何其他元素的属性。</span><span class="sxs-lookup"><span data-stu-id="8378d-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="8378d-107">应用程序将自动使用不同的操作系统的一种本地化语言到另一个使用默认系统字体。</span><span class="sxs-lookup"><span data-stu-id="8378d-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="8378d-108">应用程序运行时，系统将自动为在操作系统中选定的区域性提供正确的字体。</span><span class="sxs-lookup"><span data-stu-id="8378d-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="8378d-109">没有不设置字体，即对于更改字体样式规则的例外。</span><span class="sxs-lookup"><span data-stu-id="8378d-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="8378d-110">这可能会在其中用户单击按钮以粗体使文字在文本框中显示的应用程序很重要。</span><span class="sxs-lookup"><span data-stu-id="8378d-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="8378d-111">为此，请将编写一个函数来更改文本框中的字体样式为加粗，基于任何窗体的字体。</span><span class="sxs-lookup"><span data-stu-id="8378d-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="8378d-112">务必要在两个位置中调用此函数： 中按钮的<xref:System.Windows.Forms.Control.Click>事件处理程序并在<xref:System.Windows.Forms.Control.FontChanged>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8378d-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="8378d-113">如果仅在调用该函数<xref:System.Windows.Forms.Control.Click>事件处理程序和其他一些代码更改整个窗体的字体系列、 文本框中不会更改与窗体的其余部分。</span><span class="sxs-lookup"><span data-stu-id="8378d-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="8378d-114">但是，当你在本地化你的应用程序时, 加粗字体可能不佳对于某些语言显示。</span><span class="sxs-lookup"><span data-stu-id="8378d-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="8378d-115">如果这是一个问题，你想让本地化人员来切换从粗体到常规文本的字体的选项。</span><span class="sxs-lookup"><span data-stu-id="8378d-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="8378d-116">由于本地化人员通常不是开发人员，且没有访问源代码，请仅对资源的文件，此选项需要在资源文件中设置。</span><span class="sxs-lookup"><span data-stu-id="8378d-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="8378d-117">若要执行此操作，将设置<xref:System.Drawing.Font.Bold%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="8378d-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="8378d-118">这会导致正在写出到资源文件，本地化人员可以在其中编辑字体设置。</span><span class="sxs-lookup"><span data-stu-id="8378d-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="8378d-119">然后，你编写代码之后`InitializeComponent`方法来重置字体基于任何窗体的字体，但使用的字体样式资源文件中指定。</span><span class="sxs-lookup"><span data-stu-id="8378d-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="8378d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8378d-120">See also</span></span>

[<span data-ttu-id="8378d-121">全球化 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="8378d-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)  
[<span data-ttu-id="8378d-122">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="8378d-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)