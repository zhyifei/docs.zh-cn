---
title: 如何：在托管 HTML 文档对象模型中更改元素的样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 804041991199dd2722e3a0f38800bafd8933bbab
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333660"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="75a50-102">如何：在托管 HTML 文档对象模型中更改元素的样式</span><span class="sxs-lookup"><span data-stu-id="75a50-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="75a50-103">可以使用以 html 格式的样式来控制文档和其元素的外观。</span><span class="sxs-lookup"><span data-stu-id="75a50-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <xref:System.Windows.Forms.HtmlDocument> <span data-ttu-id="75a50-104">并<xref:System.Windows.Forms.HtmlElement>支持<xref:System.Windows.Forms.HtmlElement.Style%2A>采用以下格式的样式字符串属性：</span><span class="sxs-lookup"><span data-stu-id="75a50-104">and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>

`name1:value1;...;nameN:valueN;`

<span data-ttu-id="75a50-105">下面是`DIV`设置为 Arial，所有文本为粗体的字体的样式字符串：</span><span class="sxs-lookup"><span data-stu-id="75a50-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>

`<DIV style="font-face:arial;font-weight:bold;">`

`Hello, world!`

`</DIV>`

<span data-ttu-id="75a50-106">操作使用的样式问题<xref:System.Windows.Forms.HtmlElement.Style%2A>属性是可以证明难以将添加到和从字符串中删除单独的样式设置。</span><span class="sxs-lookup"><span data-stu-id="75a50-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="75a50-107">例如，它将变得很复杂的过程，以便呈现斜体中前面的文本，只要用户将光标放置`DIV`，并当光标离开去掉斜体`DIV`。</span><span class="sxs-lookup"><span data-stu-id="75a50-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="75a50-108">如果您需要处理大量的这种方式中的样式，则时间将会成为一个问题。</span><span class="sxs-lookup"><span data-stu-id="75a50-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>

<span data-ttu-id="75a50-109">以下过程包含可用于轻松地处理 HTML 文档和元素的样式的代码。</span><span class="sxs-lookup"><span data-stu-id="75a50-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="75a50-110">该过程要求你知道如何在 Windows 窗体，如创建新项目并将控件添加到窗体中执行基本任务。</span><span class="sxs-lookup"><span data-stu-id="75a50-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>

### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="75a50-111">若要处理在 Windows 窗体应用程序中的样式更改</span><span class="sxs-lookup"><span data-stu-id="75a50-111">To process style changes in a Windows Forms application</span></span>

1. <span data-ttu-id="75a50-112">创建新的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="75a50-112">Create a new Windows Forms project.</span></span>

2. <span data-ttu-id="75a50-113">创建新的类文件适合于您的编程语言的扩展中结束。</span><span class="sxs-lookup"><span data-stu-id="75a50-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>

3. <span data-ttu-id="75a50-114">复制`StyleGenerator`类到类文件中，在本主题的示例部分中的代码并保存代码。</span><span class="sxs-lookup"><span data-stu-id="75a50-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>

4. <span data-ttu-id="75a50-115">将以下 HTML 保存到名为 Test.htm 的文件。</span><span class="sxs-lookup"><span data-stu-id="75a50-115">Save the following HTML to a file named Test.htm.</span></span>

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. <span data-ttu-id="75a50-116">添加<xref:System.Windows.Forms.WebBrowser>名为控件`webBrowser1`到你的项目的主窗体。</span><span class="sxs-lookup"><span data-stu-id="75a50-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>

6. <span data-ttu-id="75a50-117">将以下代码添加到你的项目的代码文件。</span><span class="sxs-lookup"><span data-stu-id="75a50-117">Add the following code to your project's code file.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="75a50-118">絋粄`webBrowser1_DocumentCompleted`事件处理程序配置为侦听<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="75a50-118">Ensure that the `webBrowser1_DocumentCompleted` event hander is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="75a50-119">在 Visual Studio 中，双击<xref:System.Windows.Forms.WebBrowser>控制; 请在文本编辑器中，以编程方式配置侦听器。</span><span class="sxs-lookup"><span data-stu-id="75a50-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>  
  
     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7. <span data-ttu-id="75a50-120">运行该项目。</span><span class="sxs-lookup"><span data-stu-id="75a50-120">Run the project.</span></span> <span data-ttu-id="75a50-121">通过在第一个运行光标`DIV`以观察代码的影响。</span><span class="sxs-lookup"><span data-stu-id="75a50-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a50-122">示例</span><span class="sxs-lookup"><span data-stu-id="75a50-122">Example</span></span>  
 <span data-ttu-id="75a50-123">下面的代码示例演示的完整代码`StyleGenerator`类，该类将现有的样式值的分析，支持添加、 更改和移除样式，并返回新的样式值与所请求的更改。</span><span class="sxs-lookup"><span data-stu-id="75a50-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>  
  
 [!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="75a50-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="75a50-124">See also</span></span>

- <xref:System.Windows.Forms.HtmlElement>
