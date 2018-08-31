---
title: 将数据存储到剪贴板以及从剪贴板读取数据 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 7964a39bb84ac6af6b6c196c053f51c30301985c
ms.sourcegitcommit: 8c6c62ba1eefa492701e264e41890ee20fae77a3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "42792356"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="786c8-102">将数据存储到剪贴板以及从剪贴板读取数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="786c8-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="786c8-103">剪贴板可用于存储文本和图像等数据。</span><span class="sxs-lookup"><span data-stu-id="786c8-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="786c8-104">由于所有活动进程都共享剪贴板，因此它可用于在这些活动进程之间传输数据。</span><span class="sxs-lookup"><span data-stu-id="786c8-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="786c8-105">使用 `My.Computer.Clipboard` 对象可轻松访问剪贴板并从中读取和向其写入数据。</span><span class="sxs-lookup"><span data-stu-id="786c8-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="786c8-106">从剪贴板读取数据</span><span class="sxs-lookup"><span data-stu-id="786c8-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="786c8-107">使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> 方法读取剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="786c8-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="786c8-108">下面的代码读取文本并将其显示在消息框中。</span><span class="sxs-lookup"><span data-stu-id="786c8-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="786c8-109">剪贴板中必须存储文本该示例才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="786c8-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 <span data-ttu-id="786c8-110">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="786c8-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="786c8-111">在代码片段选取器中，它位于“Windows 窗体应用程序”>“剪贴板”中。</span><span class="sxs-lookup"><span data-stu-id="786c8-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="786c8-112">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="786c8-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="786c8-113">使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> 方法从剪贴板检索图像。</span><span class="sxs-lookup"><span data-stu-id="786c8-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="786c8-114">本示例先检查剪贴板中是否存在图像，然后再检索图像并将其分配给 `PictureBox1`。</span><span class="sxs-lookup"><span data-stu-id="786c8-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 <span data-ttu-id="786c8-115">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="786c8-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="786c8-116">在代码片段选取器中，它位于“Windows 窗体应用程序”>“剪贴板”中。有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="786c8-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="786c8-117">即使在关闭应用程序后，剪贴板中存储的项仍将保留。</span><span class="sxs-lookup"><span data-stu-id="786c8-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="786c8-118">确定存储在剪贴板中的文件类型</span><span class="sxs-lookup"><span data-stu-id="786c8-118">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="786c8-119">剪贴板中的数据可以采用多种形式，如文本、音频文件或图像。</span><span class="sxs-lookup"><span data-stu-id="786c8-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="786c8-120">若要确定哪种文件位于剪贴板中，可以使用如 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>、<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>、<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> 和 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> 的方法。</span><span class="sxs-lookup"><span data-stu-id="786c8-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="786c8-121">如果有想要检查的自定义格式，可以使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="786c8-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="786c8-122">使用 `ContainsImage` 函数可确定剪贴板中的数据是否为图像。</span><span class="sxs-lookup"><span data-stu-id="786c8-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="786c8-123">下面的代码检查数据是否为图像并相应地进行报告。</span><span class="sxs-lookup"><span data-stu-id="786c8-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="786c8-124">清除剪贴板</span><span class="sxs-lookup"><span data-stu-id="786c8-124">Clearing the Clipboard</span></span>  
 <span data-ttu-id="786c8-125"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> 方法可以清除剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="786c8-126">由于剪贴板被其他进程共享，清除它可能会影响这些进程。</span><span class="sxs-lookup"><span data-stu-id="786c8-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="786c8-127">下面的代码演示如何使用 `Clear` 方法。</span><span class="sxs-lookup"><span data-stu-id="786c8-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="786c8-128">写入剪贴板</span><span class="sxs-lookup"><span data-stu-id="786c8-128">Writing to the Clipboard</span></span>  
 <span data-ttu-id="786c8-129">使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> 方法将文本写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="786c8-130">下面的代码将字符串“This is a test string”写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 <span data-ttu-id="786c8-131">`SetText` 方法可接受包含 <xref:System.Windows.Forms.TextDataFormat> 类型的格式参数。</span><span class="sxs-lookup"><span data-stu-id="786c8-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="786c8-132">下面的代码可将字符串“This is a test string”以 RTF 文本格式写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 <span data-ttu-id="786c8-133">使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> 方法将数据写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="786c8-134">此示例以自定义格式 `specialFormat` 向剪贴板写入 `DataObject` `dataChunk`。</span><span class="sxs-lookup"><span data-stu-id="786c8-134">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 <span data-ttu-id="786c8-135">使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> 方法将音频数据写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="786c8-136">此示例将创建字节数组 `musicReader`，向其中读取文件 `cool.wav`，然后将其写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="786c8-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="786c8-137">由于其他用户可访问剪贴板，不要将其用于存储密码或机密数据等敏感信息。</span><span class="sxs-lookup"><span data-stu-id="786c8-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786c8-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="786c8-138">See also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [<span data-ttu-id="786c8-139">如何：从 XML 文件中读取对象数据</span><span class="sxs-lookup"><span data-stu-id="786c8-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="786c8-140">如何：将对象数据写入 XML 文件</span><span class="sxs-lookup"><span data-stu-id="786c8-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
