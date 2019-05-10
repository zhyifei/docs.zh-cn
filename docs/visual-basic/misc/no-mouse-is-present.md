---
title: 没有鼠标
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: 5493cea8c87a40b0c9663aaa7f36ce6cb423d346
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624865"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="d31d5-102">没有鼠标</span><span class="sxs-lookup"><span data-stu-id="d31d5-102">No mouse is present</span></span>
<span data-ttu-id="d31d5-103">调用了 `My.Computer.Mouse` 对象的一个属性，但是计算机未安装鼠标或鼠标端口。</span><span class="sxs-lookup"><span data-stu-id="d31d5-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d31d5-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d31d5-104">To correct this error</span></span>  
  
- <span data-ttu-id="d31d5-105">在调用周围将 `Try...Catch` 块添加到 `My.Computer.Mouse` 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d31d5-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="d31d5-106">— 或 —</span><span class="sxs-lookup"><span data-stu-id="d31d5-106">— or —</span></span>  
  
- <span data-ttu-id="d31d5-107">在计算机上安装鼠标。</span><span class="sxs-lookup"><span data-stu-id="d31d5-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31d5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d31d5-108">See also</span></span>

- [<span data-ttu-id="d31d5-109">My.Computer.Mouse</span><span class="sxs-lookup"><span data-stu-id="d31d5-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="d31d5-110">在 .NET 中处理和引发异常</span><span class="sxs-lookup"><span data-stu-id="d31d5-110">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="d31d5-111">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="d31d5-111">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
