---
title: "如何：从 Windows 窗体中播放提示音"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e214b368b65797100722cb41ad6a77ecd16424de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="e9c91-102">如何：从 Windows 窗体中播放提示音</span><span class="sxs-lookup"><span data-stu-id="e9c91-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="e9c91-103">本示例在运行时播放提示音。</span><span class="sxs-lookup"><span data-stu-id="e9c91-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9c91-104">示例</span><span class="sxs-lookup"><span data-stu-id="e9c91-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="e9c91-105">C# 代码示例中播放的声音由<xref:System.Media.SystemSounds.Beep%2A>系统声音设置。</span><span class="sxs-lookup"><span data-stu-id="e9c91-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="e9c91-106">有关更多信息，请参见<xref:System.Media.SystemSounds>。</span><span class="sxs-lookup"><span data-stu-id="e9c91-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9c91-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="e9c91-107">Compiling the Code</span></span>  
 <span data-ttu-id="e9c91-108">对于 C# 中，此示例需要引用<xref:System.Media?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="e9c91-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c91-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9c91-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="e9c91-110">如何：通过 Windows 窗体播放系统提示音</span><span class="sxs-lookup"><span data-stu-id="e9c91-110">How to: Play a System Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [<span data-ttu-id="e9c91-111">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="e9c91-111">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
