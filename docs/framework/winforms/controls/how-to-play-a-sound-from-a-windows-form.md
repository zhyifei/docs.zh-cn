---
title: 如何：从 Windows 窗体播放声音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 8c70187948577064ab2471e2263e587035c41754
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662391"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="5f63d-102">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="5f63d-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="5f63d-103">本示例在运行时播放给定路径中的声音。</span><span class="sxs-lookup"><span data-stu-id="5f63d-103">This example plays a sound at a given path at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f63d-104">示例</span><span class="sxs-lookup"><span data-stu-id="5f63d-104">Example</span></span>  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5f63d-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="5f63d-105">Compiling the Code</span></span>  
 <span data-ttu-id="5f63d-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5f63d-106">This example requires:</span></span>  
  
- <span data-ttu-id="5f63d-107">即，使用有效的文件名替换文件名 `"c:\Windows\Media\chimes.wav"`。</span><span class="sxs-lookup"><span data-stu-id="5f63d-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
- <span data-ttu-id="5f63d-108">(C#) 的引用<xref:System.Media?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="5f63d-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5f63d-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="5f63d-109">Robust Programming</span></span>  
 <span data-ttu-id="5f63d-110">文件操作应包含在相应的结构化异常处理块内。</span><span class="sxs-lookup"><span data-stu-id="5f63d-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>  
  
 <span data-ttu-id="5f63d-111">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="5f63d-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="5f63d-112">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="5f63d-112">The path name is malformed.</span></span> <span data-ttu-id="5f63d-113">例如，它包含非法字符或它仅为空格（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="5f63d-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="5f63d-114">此路径为只读路径（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="5f63d-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="5f63d-115">此路径名为 `null`（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="5f63d-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="5f63d-116">此路径名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="5f63d-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="5f63d-117">路径无效（<xref:System.IO.DirectoryNotFoundException> 类）。</span><span class="sxs-lookup"><span data-stu-id="5f63d-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="5f63d-118">路径是仅为冒号":"(<xref:System.NotSupportedException>类)。</span><span class="sxs-lookup"><span data-stu-id="5f63d-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5f63d-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="5f63d-119">.NET Framework Security</span></span>  
 <span data-ttu-id="5f63d-120">不要根据文件的名称来判断文件的内容。</span><span class="sxs-lookup"><span data-stu-id="5f63d-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="5f63d-121">例如，文件 `Form1.vb` 可能不是 Visual Basic 源文件。</span><span class="sxs-lookup"><span data-stu-id="5f63d-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="5f63d-122">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="5f63d-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f63d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f63d-123">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="5f63d-124">如何：加载声音以异步方式在 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="5f63d-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
