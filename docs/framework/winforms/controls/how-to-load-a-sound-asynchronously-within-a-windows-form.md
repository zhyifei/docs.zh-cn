---
title: 如何：加载声音以异步方式在 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: ed1257a942eb990c9b0c6427d264013e3324326b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523670"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="6aa58-102">如何：加载声音以异步方式在 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="6aa58-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="6aa58-103">以下代码示例从 URL 异步上载了一个声音，然后在新线程中播放。</span><span class="sxs-lookup"><span data-stu-id="6aa58-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa58-104">示例</span><span class="sxs-lookup"><span data-stu-id="6aa58-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6aa58-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="6aa58-105">Compiling the Code</span></span>  
 <span data-ttu-id="6aa58-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="6aa58-106">This example requires:</span></span>  
  
-   <span data-ttu-id="6aa58-107">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="6aa58-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="6aa58-108">即，使用有效的文件名替换文件名 `"http://www.tailspintoys.com/sounds/stop.wav"`。</span><span class="sxs-lookup"><span data-stu-id="6aa58-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="6aa58-109">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa58-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6aa58-110">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="6aa58-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6aa58-111">另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="6aa58-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6aa58-112">可靠编程</span><span class="sxs-lookup"><span data-stu-id="6aa58-112">Robust Programming</span></span>  
 <span data-ttu-id="6aa58-113">文件操作应包含在相应的异常处理块内。</span><span class="sxs-lookup"><span data-stu-id="6aa58-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="6aa58-114">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="6aa58-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6aa58-115">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="6aa58-115">The path name is malformed.</span></span> <span data-ttu-id="6aa58-116">例如，路径名称包含无效的字符或它仅为空白（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="6aa58-117">此路径为只读路径（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="6aa58-118">此路径名为 `Nothing`（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="6aa58-119">此路径名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="6aa58-120">此路径无效（<xref:System.IO.DirectoryNotFoundException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="6aa58-121">此路径仅为冒号“:”（<xref:System.NotSupportedException> 类）。</span><span class="sxs-lookup"><span data-stu-id="6aa58-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6aa58-122">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="6aa58-122">.NET Framework Security</span></span>  
 <span data-ttu-id="6aa58-123">不要根据文件的名称来判断文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6aa58-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="6aa58-124">例如，文件 `Form1.vb` 可能不是 Visual Basic 源文件。</span><span class="sxs-lookup"><span data-stu-id="6aa58-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="6aa58-125">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="6aa58-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa58-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa58-126">See also</span></span>
- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [<span data-ttu-id="6aa58-127">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="6aa58-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
