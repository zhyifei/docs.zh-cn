---
title: "ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5f23c3fe39adcebcfdfadb9e9c2b639f16330d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="b6d44-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="b6d44-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="b6d44-103">关闭映射信息的令牌源范围的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="b6d44-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="b6d44-104">关闭后，可以不添加任何更多的映射信息。</span><span class="sxs-lookup"><span data-stu-id="b6d44-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d44-105">语法</span><span class="sxs-lookup"><span data-stu-id="b6d44-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b6d44-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b6d44-106">Return Value</span></span>  
 <span data-ttu-id="b6d44-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="b6d44-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d44-108">要求</span><span class="sxs-lookup"><span data-stu-id="b6d44-108">Requirements</span></span>  
 <span data-ttu-id="b6d44-109">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6d44-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d44-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d44-110">See Also</span></span>  
 [<span data-ttu-id="b6d44-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="b6d44-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
