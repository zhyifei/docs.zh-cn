---
title: 没有鼠标
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: f69371ea2db1aba5d3ad501ab41a9ea6e646ad3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557872"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="c1f2f-102">没有鼠标</span><span class="sxs-lookup"><span data-stu-id="c1f2f-102">No mouse is present</span></span>
<span data-ttu-id="c1f2f-103">调用了 `My.Computer.Mouse` 对象的一个属性，但是计算机未安装鼠标或鼠标端口。</span><span class="sxs-lookup"><span data-stu-id="c1f2f-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1f2f-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c1f2f-104">To correct this error</span></span>  
  
-   <span data-ttu-id="c1f2f-105">在调用周围将 `Try...Catch` 块添加到 `My.Computer.Mouse` 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c1f2f-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="c1f2f-106">— 或 —</span><span class="sxs-lookup"><span data-stu-id="c1f2f-106">— or —</span></span>  
  
-   <span data-ttu-id="c1f2f-107">在计算机上安装鼠标。</span><span class="sxs-lookup"><span data-stu-id="c1f2f-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f2f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1f2f-108">See also</span></span>
- [<span data-ttu-id="c1f2f-109">My.Computer.Mouse</span><span class="sxs-lookup"><span data-stu-id="c1f2f-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="c1f2f-110">Visual Basic 中的异常与错误处理</span><span class="sxs-lookup"><span data-stu-id="c1f2f-110">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
- [<span data-ttu-id="c1f2f-111">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="c1f2f-111">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
