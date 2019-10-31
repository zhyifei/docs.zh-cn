---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 43c35596d31842b85bbdc96a63413a176a59a172
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121657"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="87959-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="87959-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="87959-103">关闭 "特定自定义数据" 部分以获取令牌到源范围的映射信息。</span><span class="sxs-lookup"><span data-stu-id="87959-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="87959-104">关闭后，不能再添加映射信息。</span><span class="sxs-lookup"><span data-stu-id="87959-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87959-105">语法</span><span class="sxs-lookup"><span data-stu-id="87959-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="87959-106">返回值</span><span class="sxs-lookup"><span data-stu-id="87959-106">Return Value</span></span>  
 <span data-ttu-id="87959-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="87959-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87959-108">要求</span><span class="sxs-lookup"><span data-stu-id="87959-108">Requirements</span></span>  
 <span data-ttu-id="87959-109">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="87959-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87959-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="87959-110">See also</span></span>

- [<span data-ttu-id="87959-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="87959-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
