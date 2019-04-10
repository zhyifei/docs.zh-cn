---
title: 必须首先用一个“PathName”自变量调用“Dir”函数
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323637"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="183a3-102">必须首先用一个“PathName”自变量调用“Dir”函数</span><span class="sxs-lookup"><span data-stu-id="183a3-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="183a3-103">首次调用`Dir`函数不包括`PathName`参数。</span><span class="sxs-lookup"><span data-stu-id="183a3-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="183a3-104">首次调用`Dir`必须包含`PathName`，但后续调用`Dir`无需包含参数来检索下一项。</span><span class="sxs-lookup"><span data-stu-id="183a3-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="183a3-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="183a3-105">To correct this error</span></span>  
  
1. <span data-ttu-id="183a3-106">提供`PathName`函数调用中的参数。</span><span class="sxs-lookup"><span data-stu-id="183a3-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="183a3-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="183a3-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
