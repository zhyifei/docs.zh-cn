---
title: '&#39;Dir&#39;函数必须首先调用使用&#39;PathName&#39;参数'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518483"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="9d1bd-102">&#39;Dir&#39;函数必须首先调用使用&#39;PathName&#39;参数</span><span class="sxs-lookup"><span data-stu-id="9d1bd-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="9d1bd-103">首次调用`Dir`函数不包括`PathName`参数。</span><span class="sxs-lookup"><span data-stu-id="9d1bd-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="9d1bd-104">首次调用`Dir`必须包含`PathName`，但后续调用`Dir`无需包含参数来检索下一项。</span><span class="sxs-lookup"><span data-stu-id="9d1bd-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d1bd-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9d1bd-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="9d1bd-106">提供`PathName`函数调用中的参数。</span><span class="sxs-lookup"><span data-stu-id="9d1bd-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1bd-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d1bd-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
