---
title: "播放声音 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8be5cec634482bf99ddff4ff6b6af8e897c4909e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="c6fc8-102">播放声音 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6fc8-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="c6fc8-103">`My.Computer.Audio` 对象提供用于播放声音的方法。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="c6fc8-104">播放声音</span><span class="sxs-lookup"><span data-stu-id="c6fc8-104">Playing Sounds</span></span>  
 <span data-ttu-id="c6fc8-105">应用程序可通过背景播放在播放声音时执行其他代码。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="c6fc8-106">`My.Computer.Audio.Play` 方法允许应用程序一次仅播放一种背景声音；应用程序播放新背景声音时，会停止播放上一种背景声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="c6fc8-107">你也可以播放一种声音并等待其播放完毕。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="c6fc8-108">下例中使用 `My.Computer.Audio.Play` 方法播放声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="c6fc8-109">指定 `AudioPlayMode.WaitToComplete` 时，`My.Computer.Audio.Play` 将等待声音播放完毕，然后再调用代码继续。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="c6fc8-110">使用此示例时，应确保文件名可指代计算机中的 .wav 声音文件</span><span class="sxs-lookup"><span data-stu-id="c6fc8-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 <span data-ttu-id="c6fc8-111">下例中使用 `My.Computer.Audio.Play` 方法播放声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="c6fc8-112">使用此示例时，应确保应用程序资源包含名为 Waterfall 的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="c6fc8-113">播放循环声音</span><span class="sxs-lookup"><span data-stu-id="c6fc8-113">Playing Looping Sounds</span></span>  
 <span data-ttu-id="c6fc8-114">在下例中，指定 `PlayMode.BackgroundLoop` 时，`My.Computer.Audio.Play` 方法将播放指定的背景声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="c6fc8-115">使用此示例时，应确保文件名可指代计算机中的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 <span data-ttu-id="c6fc8-116">在下例中，指定 `PlayMode.BackgroundLoop` 时，`My.Computer.Audio.Play` 方法将播放指定的背景声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="c6fc8-117">使用此示例时，应确保应用程序资源包含名为 Waterfall 的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 <span data-ttu-id="c6fc8-118">前面的代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c6fc8-119">在代码片段选取器中，它位于“Windows 窗体应用程序”>“声音”中。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="c6fc8-120">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="c6fc8-121">一般情况下，应用程序播放循环声音时，声音最终将停止。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="c6fc8-122">停止播放背景声音</span><span class="sxs-lookup"><span data-stu-id="c6fc8-122">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="c6fc8-123">使用 `My.Computer.Audio.Stop` 方法可停止应用程序当前播放的背景声音或循环声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="c6fc8-124">一般情况下，应用程序播放循环声音时，声音将在某个时间点停止。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="c6fc8-125">下面的示例将停止播放背景声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 <span data-ttu-id="c6fc8-126">前面的代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c6fc8-127">在代码片段选取器中，它位于“Windows 窗体应用程序”>“声音”中。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="c6fc8-128">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="c6fc8-129">播放系统声音</span><span class="sxs-lookup"><span data-stu-id="c6fc8-129">Playing System Sounds</span></span>  
 <span data-ttu-id="c6fc8-130">使用 `My.Computer.Audio.PlaySystemSound` 方法可播放指定的系统声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="c6fc8-131">`My.Computer.Audio.PlaySystemSound` 方法将作为 <xref:System.Media.SystemSound> 类中的共享成员之一的参数。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="c6fc8-132">系统声音 <xref:System.Media.SystemSounds.Asterisk%2A> 通常表示错误。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="c6fc8-133">下例使用 `My.Computer.Audio.PlaySystemSound` 方法播放系统声音。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c6fc8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6fc8-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>  
 <xref:Microsoft.VisualBasic.AudioPlayMode>
