---
title: "播放声音 (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="49434-102">播放声音 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49434-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="49434-103">`My.Computer.Audio` 对象提供用于播放声音的方法。</span><span class="sxs-lookup"><span data-stu-id="49434-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="49434-104">播放声音</span><span class="sxs-lookup"><span data-stu-id="49434-104">Playing Sounds</span></span>  
 <span data-ttu-id="49434-105">应用程序可通过背景播放在播放声音时执行其他代码。</span><span class="sxs-lookup"><span data-stu-id="49434-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="49434-106">`My.Computer.Audio.Play` 方法允许应用程序一次仅播放一种背景声音；应用程序播放新背景声音时，会停止播放上一种背景声音。</span><span class="sxs-lookup"><span data-stu-id="49434-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="49434-107">你也可以播放一种声音并等待其播放完毕。</span><span class="sxs-lookup"><span data-stu-id="49434-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="49434-108">下例中使用 `My.Computer.Audio.Play` 方法播放声音。</span><span class="sxs-lookup"><span data-stu-id="49434-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="49434-109">指定 `AudioPlayMode.WaitToComplete` 时，`My.Computer.Audio.Play` 将等待声音播放完毕，然后再调用代码继续。</span><span class="sxs-lookup"><span data-stu-id="49434-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="49434-110">使用此示例时，应确保文件名可指代计算机中的 .wav 声音文件</span><span class="sxs-lookup"><span data-stu-id="49434-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="49434-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="49434-112">下例中使用 `My.Computer.Audio.Play` 方法播放声音。</span><span class="sxs-lookup"><span data-stu-id="49434-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="49434-113">使用此示例时，应确保应用程序资源包含名为 Waterfall 的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="49434-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="49434-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="49434-115">播放循环声音</span><span class="sxs-lookup"><span data-stu-id="49434-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="49434-116">在下例中，指定 `PlayMode.BackgroundLoop` 时，`My.Computer.Audio.Play` 方法将播放指定的背景声音。</span><span class="sxs-lookup"><span data-stu-id="49434-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="49434-117">使用此示例时，应确保文件名可指代计算机中的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="49434-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="49434-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="49434-119">在下例中，指定 `PlayMode.BackgroundLoop` 时，`My.Computer.Audio.Play` 方法将播放指定的背景声音。</span><span class="sxs-lookup"><span data-stu-id="49434-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="49434-120">使用此示例时，应确保应用程序资源包含名为 Waterfall 的 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="49434-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="49434-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="49434-122">前面的代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="49434-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="49434-123">在代码片段选取器中，它位于“Windows 窗体应用程序”>“声音”中。</span><span class="sxs-lookup"><span data-stu-id="49434-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="49434-124">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="49434-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="49434-125">一般情况下，应用程序播放循环声音时，声音最终将停止。</span><span class="sxs-lookup"><span data-stu-id="49434-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="49434-126">停止播放背景声音</span><span class="sxs-lookup"><span data-stu-id="49434-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="49434-127">使用 `My.Computer.Audio.Stop` 方法可停止应用程序当前播放的背景声音或循环声音。</span><span class="sxs-lookup"><span data-stu-id="49434-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="49434-128">一般情况下，应用程序播放循环声音时，声音将在某个时间点停止。</span><span class="sxs-lookup"><span data-stu-id="49434-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="49434-129">下面的示例将停止播放背景声音。</span><span class="sxs-lookup"><span data-stu-id="49434-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="49434-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="49434-131">前面的代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="49434-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="49434-132">在代码片段选取器中，它位于“Windows 窗体应用程序”>“声音”中。</span><span class="sxs-lookup"><span data-stu-id="49434-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="49434-133">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="49434-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="49434-134">播放系统声音</span><span class="sxs-lookup"><span data-stu-id="49434-134">Playing System Sounds</span></span>  
 <span data-ttu-id="49434-135">使用 `My.Computer.Audio.PlaySystemSound` 方法可播放指定的系统声音。</span><span class="sxs-lookup"><span data-stu-id="49434-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="49434-136">`My.Computer.Audio.PlaySystemSound` 方法将作为 <xref:System.Media.SystemSound> 类中的共享成员之一的参数。</span><span class="sxs-lookup"><span data-stu-id="49434-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="49434-137">系统声音 <xref:System.Media.SystemSounds.Asterisk%2A> 通常表示错误。</span><span class="sxs-lookup"><span data-stu-id="49434-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="49434-138">下例使用 `My.Computer.Audio.PlaySystemSound` 方法播放系统声音。</span><span class="sxs-lookup"><span data-stu-id="49434-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="49434-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="49434-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49434-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49434-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

