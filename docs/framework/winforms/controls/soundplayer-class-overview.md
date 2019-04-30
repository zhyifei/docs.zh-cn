---
title: SoundPlayer 类概述
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971998"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="ec2f1-102">SoundPlayer 类概述</span><span class="sxs-lookup"><span data-stu-id="ec2f1-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="ec2f1-103"><xref:System.Media.SoundPlayer> 类使你能够轻松地将声音纳入应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="ec2f1-104"><xref:System.Media.SoundPlayer>类可播放资源或者 UNC 或 HTTP 位置中.wav 格式的声音文件。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="ec2f1-105">此外，<xref:System.Media.SoundPlayer>类，可加载或以异步方式播放声音。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="ec2f1-106">还可使用 <xref:System.Media.SystemSounds> 类播放常见的系统声音，包括提示音。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="ec2f1-107">常用的属性、方法和事件</span><span class="sxs-lookup"><span data-stu-id="ec2f1-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="ec2f1-108">名称</span><span class="sxs-lookup"><span data-stu-id="ec2f1-108">Name</span></span>|<span data-ttu-id="ec2f1-109">描述</span><span class="sxs-lookup"><span data-stu-id="ec2f1-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ec2f1-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="ec2f1-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="ec2f1-111">声音的文件路径或 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="ec2f1-112">可接受的值可以是 UNC 或 HTTP。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="ec2f1-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="ec2f1-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="ec2f1-114">程序引发异常前等待加载声音的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="ec2f1-115">默认值为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="ec2f1-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="ec2f1-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="ec2f1-117">一个指示声音是否加载完毕的布尔值。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="ec2f1-118"><xref:System.Media.SoundPlayer.Load%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="ec2f1-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="ec2f1-119">同步加载声音。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="ec2f1-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="ec2f1-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="ec2f1-121">开始异步加载声音。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="ec2f1-122">加载完成后，它会发出<xref:System.Media.SoundPlayer.OnLoadCompleted%2A>事件。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="ec2f1-123"><xref:System.Media.SoundPlayer.Play%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="ec2f1-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="ec2f1-124">在指定的声音<xref:System.Media.SoundPlayer.SoundLocation%2A>或<xref:System.Media.SoundPlayer.Stream%2A>新线程中的属性。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="ec2f1-125"><xref:System.Media.SoundPlayer.PlaySync%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="ec2f1-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="ec2f1-126">在指定的声音<xref:System.Media.SoundPlayer.SoundLocation%2A>或<xref:System.Media.SoundPlayer.Stream%2A>当前线程中的属性。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="ec2f1-127"><xref:System.Media.SoundPlayer.Stop%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="ec2f1-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="ec2f1-128">停止当前播放的任何声音。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="ec2f1-129"><xref:System.Media.SoundPlayer.LoadCompleted> 事件</span><span class="sxs-lookup"><span data-stu-id="ec2f1-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="ec2f1-130">尝试加载声音后引发。</span><span class="sxs-lookup"><span data-stu-id="ec2f1-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec2f1-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec2f1-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
