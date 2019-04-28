---
title: 如何：从 Windows 窗体播放提示音
ms.date: 03/30/2017
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
ms.openlocfilehash: 0aa01f600873dd8853e1c33d5443448835e11455
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913427"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="499b6-102">如何：从 Windows 窗体播放提示音</span><span class="sxs-lookup"><span data-stu-id="499b6-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="499b6-103">本示例在运行时播放提示音。</span><span class="sxs-lookup"><span data-stu-id="499b6-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="499b6-104">示例</span><span class="sxs-lookup"><span data-stu-id="499b6-104">Example</span></span>  
  
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
>  <span data-ttu-id="499b6-105">中播放的声音C#代码示例由<xref:System.Media.SystemSounds.Beep%2A>系统声音设置决定。</span><span class="sxs-lookup"><span data-stu-id="499b6-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="499b6-106">有关详细信息，请参阅 <xref:System.Media.SystemSounds>。</span><span class="sxs-lookup"><span data-stu-id="499b6-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="499b6-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="499b6-107">Compiling the Code</span></span>  
 <span data-ttu-id="499b6-108">有关C#，此示例需要引用<xref:System.Media?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="499b6-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499b6-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="499b6-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="499b6-110">如何：从 Windows 窗体播放系统声音</span><span class="sxs-lookup"><span data-stu-id="499b6-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="499b6-111">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="499b6-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
