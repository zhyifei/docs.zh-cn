---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127772"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="12d71-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="12d71-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="12d71-103">关闭令牌源跨度映射信息的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="12d71-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="12d71-104">已关闭后，可以添加未映射的更多信息。</span><span class="sxs-lookup"><span data-stu-id="12d71-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d71-105">语法</span><span class="sxs-lookup"><span data-stu-id="12d71-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="12d71-106">返回值</span><span class="sxs-lookup"><span data-stu-id="12d71-106">Return Value</span></span>  
 <span data-ttu-id="12d71-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="12d71-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12d71-108">要求</span><span class="sxs-lookup"><span data-stu-id="12d71-108">Requirements</span></span>  
 <span data-ttu-id="12d71-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12d71-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d71-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="12d71-110">See also</span></span>

- [<span data-ttu-id="12d71-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="12d71-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
