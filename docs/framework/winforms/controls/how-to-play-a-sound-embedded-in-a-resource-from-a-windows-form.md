---
title: 如何：播放从 Windows 窗体资源中嵌入的声音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: f52cac4ca16adee232fae6fe2c1540bf5d3cb8cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708179"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="491a0-102">如何：播放从 Windows 窗体资源中嵌入的声音</span><span class="sxs-lookup"><span data-stu-id="491a0-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="491a0-103">可以使用<xref:System.Media.SoundPlayer>类播放嵌入的资源中的声音。</span><span class="sxs-lookup"><span data-stu-id="491a0-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="491a0-104">示例</span><span class="sxs-lookup"><span data-stu-id="491a0-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="491a0-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="491a0-105">Compiling the Code</span></span>  
 <span data-ttu-id="491a0-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="491a0-106">This example requires:</span></span>  
  
 <span data-ttu-id="491a0-107">导入<xref:System.Media?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="491a0-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="491a0-108">将声音文件作为嵌入资源包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="491a0-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="491a0-109">将“\<程序集名称>”替换为嵌入声音文件的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="491a0-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="491a0-110">不要包含“.dll”后缀。</span><span class="sxs-lookup"><span data-stu-id="491a0-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491a0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="491a0-111">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="491a0-112">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="491a0-112">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="491a0-113">如何：循环上的 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="491a0-113">How to: Loop a Sound Playing on a Windows Form</span></span>](how-to-loop-a-sound-playing-on-a-windows-form.md)
