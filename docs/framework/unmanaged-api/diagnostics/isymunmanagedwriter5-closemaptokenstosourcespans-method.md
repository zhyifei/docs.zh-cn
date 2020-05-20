---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614625"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="4d1d2-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="4d1d2-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="4d1d2-103">关闭 "特定自定义数据" 部分以获取令牌到源范围的映射信息。</span><span class="sxs-lookup"><span data-stu-id="4d1d2-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="4d1d2-104">关闭后，不能再添加映射信息。</span><span class="sxs-lookup"><span data-stu-id="4d1d2-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d1d2-105">语法</span><span class="sxs-lookup"><span data-stu-id="4d1d2-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4d1d2-106">返回值</span><span class="sxs-lookup"><span data-stu-id="4d1d2-106">Return Value</span></span>  
 <span data-ttu-id="4d1d2-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="4d1d2-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d1d2-108">要求</span><span class="sxs-lookup"><span data-stu-id="4d1d2-108">Requirements</span></span>  
 <span data-ttu-id="4d1d2-109">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="4d1d2-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1d2-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d1d2-110">See also</span></span>

- [<span data-ttu-id="4d1d2-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="4d1d2-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
