---
title: 如何：从 Windows 窗体播放资源中嵌入的声音
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
ms.openlocfilehash: c9dc8499e2d12ed17f9b409a805148d08da894fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532130"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="0ab5d-102">如何：从 Windows 窗体播放资源中嵌入的声音</span><span class="sxs-lookup"><span data-stu-id="0ab5d-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="0ab5d-103">你可以使用<xref:System.Media.SoundPlayer>类来从嵌入的资源播放声音。</span><span class="sxs-lookup"><span data-stu-id="0ab5d-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ab5d-104">示例</span><span class="sxs-lookup"><span data-stu-id="0ab5d-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ab5d-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="0ab5d-105">Compiling the Code</span></span>  
 <span data-ttu-id="0ab5d-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0ab5d-106">This example requires:</span></span>  
  
 <span data-ttu-id="0ab5d-107">导入<xref:System.Media?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="0ab5d-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="0ab5d-108">将声音文件作为嵌入资源包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="0ab5d-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="0ab5d-109">将“\<程序集名称>”替换为嵌入声音文件的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="0ab5d-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="0ab5d-110">不要包含“.dll”后缀。</span><span class="sxs-lookup"><span data-stu-id="0ab5d-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab5d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ab5d-111">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="0ab5d-112">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="0ab5d-112">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="0ab5d-113">如何：在 Windows 窗体上循环播放声音</span><span class="sxs-lookup"><span data-stu-id="0ab5d-113">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
