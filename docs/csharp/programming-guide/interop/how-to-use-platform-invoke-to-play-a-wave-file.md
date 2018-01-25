---
title: "如何：使用平台调用播放波形文件（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2aacad0e8004e60471a59ebef695ddae5f7a2a7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="1a2f9-102">如何：使用平台调用播放波形文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1a2f9-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="1a2f9-103">下面的 C# 代码示例说明了如何使用平台调用服务在 Windows 操作系统中播放波形声音文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a2f9-104">示例</span><span class="sxs-lookup"><span data-stu-id="1a2f9-104">Example</span></span>  
 <span data-ttu-id="1a2f9-105">此示例代码使用 `DllImport` 将 `winmm.dll` 的 `PlaySound` 方法入口点导入为 `Form1 PlaySound()`。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="1a2f9-106">本示例具有一个带按钮的简单 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="1a2f9-107">单击该按钮将打开一个标准的 Windows <xref:System.Windows.Forms.OpenFileDialog> 对话框，以便你可以打开要播放的文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="1a2f9-108">选中波形文件后，该文件将使用 winmm.DLL 程序集方法的 `PlaySound()` 方法播放。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-108">When a wave file is selected, it is played by using the `PlaySound()` method of the winmm.DLL assembly method.</span></span> <span data-ttu-id="1a2f9-109">有关 winmm.dll 的 `PlaySound` 方法的详细信息，请参阅[使用 PlaySound 功能处理波形音频文件](http://go.microsoft.com/fwlink/?LinkId=148553)。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-109">For more information about winmm.dll's `PlaySound` method, see [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).</span></span> <span data-ttu-id="1a2f9-110">浏览并选择具有 .wav 扩展名的文件，然后单击“打开”以使用平台调用播放波形文件。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="1a2f9-111">文本框中显示所选文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="1a2f9-112">通过筛选器设置对“打开文件”对话框进行筛选，以仅显示扩展名为 .wav 的文件：</span><span class="sxs-lookup"><span data-stu-id="1a2f9-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a2f9-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="1a2f9-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="1a2f9-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="1a2f9-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="1a2f9-115">在 Visual Studio 中创建新的 C# Windows 应用程序项目，然后将其命名为“WinSound”。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="1a2f9-116">复制上面的代码，然后将其粘贴到 `Form1.cs` 文件的内容上。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="1a2f9-117">复制以下代码，然后用 `InitializeComponent()` 方法将其粘贴到 `Form1.Designer.cs` 文件中任何现有代码之后。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="1a2f9-118">编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1a2f9-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="1a2f9-119">.NET Framework Security</span></span>  
 <span data-ttu-id="1a2f9-120">有关详细信息，请参阅 [.NET Framework 安全性](http://go.microsoft.com/fwlink/?LinkId=37122)。</span><span class="sxs-lookup"><span data-stu-id="1a2f9-120">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2f9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a2f9-121">See Also</span></span>  
 [<span data-ttu-id="1a2f9-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1a2f9-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1a2f9-123">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="1a2f9-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="1a2f9-124">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="1a2f9-124">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="1a2f9-125">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="1a2f9-125">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="1a2f9-126">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="1a2f9-126">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
