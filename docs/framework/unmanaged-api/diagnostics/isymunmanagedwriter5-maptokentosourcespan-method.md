---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan 方法
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf061de3e75550e33ba67c1d624279b1673c5382
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465331"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="2009f-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 方法</span><span class="sxs-lookup"><span data-stu-id="2009f-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="2009f-103">映射到给定的源行的给定元数据标记跨越中指定的源文件中。</span><span class="sxs-lookup"><span data-stu-id="2009f-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="2009f-104">必须调用之间调用[OpenMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)并[CloseMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2009f-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2009f-105">语法</span><span class="sxs-lookup"><span data-stu-id="2009f-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2009f-106">参数</span><span class="sxs-lookup"><span data-stu-id="2009f-106">Parameters</span></span>  
  
|<span data-ttu-id="2009f-107">参数</span><span class="sxs-lookup"><span data-stu-id="2009f-107">Parameter</span></span>|<span data-ttu-id="2009f-108">描述</span><span class="sxs-lookup"><span data-stu-id="2009f-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="2009f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2009f-109">Return Value</span></span>  
 <span data-ttu-id="2009f-110">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="2009f-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2009f-111">要求</span><span class="sxs-lookup"><span data-stu-id="2009f-111">Requirements</span></span>  
 <span data-ttu-id="2009f-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2009f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2009f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2009f-113">See also</span></span>
- [<span data-ttu-id="2009f-114">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="2009f-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
