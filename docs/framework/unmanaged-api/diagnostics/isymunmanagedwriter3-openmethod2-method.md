---
title: "ISymUnmanagedWriter3::OpenMethod2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.OpenMethod2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8da6de0271ddce5b956e667420a206c09cc291d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="942ef-102">ISymUnmanagedWriter3::OpenMethod2 方法</span><span class="sxs-lookup"><span data-stu-id="942ef-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="942ef-103">打开一个方法，并提供其实际节偏移量在映像中。</span><span class="sxs-lookup"><span data-stu-id="942ef-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="942ef-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="942ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="942ef-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="942ef-106">[in]若要打开方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="942ef-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="942ef-107">[in]映像中的部分偏移量。</span><span class="sxs-lookup"><span data-stu-id="942ef-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="942ef-108">[in]映像中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="942ef-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="942ef-109">返回值</span><span class="sxs-lookup"><span data-stu-id="942ef-109">Return Value</span></span>  
 <span data-ttu-id="942ef-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="942ef-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="942ef-111">惠?</span><span class="sxs-lookup"><span data-stu-id="942ef-111">Requirements</span></span>  
 <span data-ttu-id="942ef-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="942ef-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942ef-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="942ef-113">See Also</span></span>  
 [<span data-ttu-id="942ef-114">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="942ef-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="942ef-115">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="942ef-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
