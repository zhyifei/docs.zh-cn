---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 653dd933066898c1954cfbcc57c0c0493e47b4be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428607"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="2b0ca-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="2b0ca-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="2b0ca-103">关闭映射信息的令牌源范围的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="2b0ca-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="2b0ca-104">关闭后，可以不添加任何更多的映射信息。</span><span class="sxs-lookup"><span data-stu-id="2b0ca-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b0ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b0ca-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2b0ca-106">返回值</span><span class="sxs-lookup"><span data-stu-id="2b0ca-106">Return Value</span></span>  
 <span data-ttu-id="2b0ca-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="2b0ca-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b0ca-108">要求</span><span class="sxs-lookup"><span data-stu-id="2b0ca-108">Requirements</span></span>  
 <span data-ttu-id="2b0ca-109">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b0ca-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b0ca-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b0ca-110">See Also</span></span>  
 [<span data-ttu-id="2b0ca-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="2b0ca-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
