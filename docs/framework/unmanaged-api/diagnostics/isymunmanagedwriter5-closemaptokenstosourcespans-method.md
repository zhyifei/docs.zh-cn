---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4b41854d5d9324169b1873f431ef81c0a4c5be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677913"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="31f58-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="31f58-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="31f58-103">关闭令牌源跨度映射信息的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="31f58-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="31f58-104">已关闭后，可以添加未映射的更多信息。</span><span class="sxs-lookup"><span data-stu-id="31f58-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f58-105">语法</span><span class="sxs-lookup"><span data-stu-id="31f58-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="31f58-106">返回值</span><span class="sxs-lookup"><span data-stu-id="31f58-106">Return Value</span></span>  
 <span data-ttu-id="31f58-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="31f58-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f58-108">要求</span><span class="sxs-lookup"><span data-stu-id="31f58-108">Requirements</span></span>  
 <span data-ttu-id="31f58-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31f58-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f58-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="31f58-110">See also</span></span>
- [<span data-ttu-id="31f58-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="31f58-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
