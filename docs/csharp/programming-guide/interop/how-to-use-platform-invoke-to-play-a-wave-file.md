---
title: 如何：使用平台调用播放波形文件 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 101cd6fa044e181cf6f993fbea642c9dffe04008
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236851"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="81e30-102">如何：使用平台调用播放波形文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="81e30-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="81e30-103">下面的 C# 代码示例说明了如何使用平台调用服务在 Windows 操作系统中播放波形声音文件。</span><span class="sxs-lookup"><span data-stu-id="81e30-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81e30-104">示例</span><span class="sxs-lookup"><span data-stu-id="81e30-104">Example</span></span>  
 <span data-ttu-id="81e30-105">此示例代码使用 `DllImport` 将 `winmm.dll` 的 `PlaySound` 方法入口点导入为 `Form1 PlaySound()`。</span><span class="sxs-lookup"><span data-stu-id="81e30-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="81e30-106">本示例具有一个带按钮的简单 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="81e30-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="81e30-107">单击该按钮将打开一个标准的 Windows <xref:System.Windows.Forms.OpenFileDialog> 对话框，以便你可以打开要播放的文件。</span><span class="sxs-lookup"><span data-stu-id="81e30-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="81e30-108">选中波形文件时，将使用 `winmm.dll` 库的 `PlaySound()` 方法进行播放。</span><span class="sxs-lookup"><span data-stu-id="81e30-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="81e30-109">有关此方法的详细信息，请参阅[使用 PlaySound 功能处理波形音频文件](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files)。</span><span class="sxs-lookup"><span data-stu-id="81e30-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="81e30-110">浏览并选择具有 .wav 扩展名的文件，然后单击“打开”以使用平台调用播放波形文件。</span><span class="sxs-lookup"><span data-stu-id="81e30-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="81e30-111">文本框中显示所选文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="81e30-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="81e30-112">通过筛选器设置对“打开文件”对话框进行筛选，以仅显示扩展名为 .wav 的文件：</span><span class="sxs-lookup"><span data-stu-id="81e30-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81e30-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="81e30-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="81e30-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="81e30-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="81e30-115">在 Visual Studio 中创建新的 C# Windows 应用程序项目，然后将其命名为“WinSound”。</span><span class="sxs-lookup"><span data-stu-id="81e30-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="81e30-116">复制上面的代码，然后将其粘贴到 `Form1.cs` 文件的内容上。</span><span class="sxs-lookup"><span data-stu-id="81e30-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="81e30-117">复制以下代码，然后用 `InitializeComponent()` 方法将其粘贴到 `Form1.Designer.cs` 文件中任何现有代码之后。</span><span class="sxs-lookup"><span data-stu-id="81e30-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="81e30-118">编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="81e30-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="81e30-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="81e30-119">.NET Framework Security</span></span>  
 <span data-ttu-id="81e30-120">有关详细信息，请参阅 [ .NET 中的安全性](../../../standard/security/index.md)。</span><span class="sxs-lookup"><span data-stu-id="81e30-120">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e30-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="81e30-121">See Also</span></span>

- [<span data-ttu-id="81e30-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="81e30-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="81e30-123">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="81e30-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
- [<span data-ttu-id="81e30-124">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="81e30-124">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
- [<span data-ttu-id="81e30-125">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="81e30-125">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
