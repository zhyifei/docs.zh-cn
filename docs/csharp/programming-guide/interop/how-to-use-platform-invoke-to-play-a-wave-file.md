---
title: 如何使用平台调用播放 WAV 文件 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 3ea90f0739ad45c31e4f25836c9de8e708dff2cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700817"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="10fdb-102">如何使用平台调用播放 WAV 文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="10fdb-102">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="10fdb-103">下面的 C# 代码示例说明了如何使用平台调用服务在 Windows 操作系统中播放 WAV 声音文件。</span><span class="sxs-lookup"><span data-stu-id="10fdb-103">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="10fdb-104">示例</span><span class="sxs-lookup"><span data-stu-id="10fdb-104">Example</span></span>

<span data-ttu-id="10fdb-105">此示例代码使用 <xref:System.Runtime.InteropServices.DllImportAttribute> 将 `winmm.dll` 的 `PlaySound` 方法入口点导入为 `Form1 PlaySound()`。</span><span class="sxs-lookup"><span data-stu-id="10fdb-105">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="10fdb-106">本示例具有一个带按钮的简单 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="10fdb-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="10fdb-107">单击该按钮将打开一个标准的 Windows <xref:System.Windows.Forms.OpenFileDialog> 对话框，以便你可以打开要播放的文件。</span><span class="sxs-lookup"><span data-stu-id="10fdb-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="10fdb-108">选中波形文件后，该文件将使用 winmm.dll 库的 `PlaySound()` 方法播放。</span><span class="sxs-lookup"><span data-stu-id="10fdb-108">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="10fdb-109">有关此方法的详细信息，请参阅[使用 PlaySound 功能处理波形音频文件](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files)。</span><span class="sxs-lookup"><span data-stu-id="10fdb-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="10fdb-110">浏览并选择具有 .wav 扩展名的文件，然后单击“打开”  以使用平台调用播放波形文件。</span><span class="sxs-lookup"><span data-stu-id="10fdb-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="10fdb-111">文本框中显示所选文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="10fdb-111">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="10fdb-112">通过筛选器设置对“打开文件”  对话框进行筛选，以仅显示扩展名为 .wav 的文件：</span><span class="sxs-lookup"><span data-stu-id="10fdb-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="10fdb-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="10fdb-113">Compiling the code</span></span>

1. <span data-ttu-id="10fdb-114">在 Visual Studio 中创建一个新的 C# Windows Forms 应用程序项目，并将其命名为“WinSound”  。</span><span class="sxs-lookup"><span data-stu-id="10fdb-114">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="10fdb-115">复制上面的代码，将其粘贴到 Form1.cs  文件的内容中。</span><span class="sxs-lookup"><span data-stu-id="10fdb-115">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="10fdb-116">复制以下代码，然后将其粘贴到 `InitializeComponent()` 方法中 Form1.Designer.cs 文件的任何现有代码之后。</span><span class="sxs-lookup"><span data-stu-id="10fdb-116">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="10fdb-117">编译并运行该代码。</span><span class="sxs-lookup"><span data-stu-id="10fdb-117">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="10fdb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10fdb-118">See also</span></span>

- [<span data-ttu-id="10fdb-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="10fdb-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="10fdb-120">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="10fdb-120">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="10fdb-121">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="10fdb-121">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="10fdb-122">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="10fdb-122">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
