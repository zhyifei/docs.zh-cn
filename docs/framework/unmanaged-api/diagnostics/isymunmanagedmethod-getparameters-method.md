---
title: "ISymUnmanagedMethod::GetParameters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetParameters
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a2e3471b63f819bfe1879b87e42ff9258036356
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="46423-102">ISymUnmanagedMethod::GetParameters 方法</span><span class="sxs-lookup"><span data-stu-id="46423-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="46423-103">获取此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="46423-103">Gets the parameters for this method.</span></span> <span data-ttu-id="46423-104">参数是在方法的签名中定义的顺序返回。</span><span class="sxs-lookup"><span data-stu-id="46423-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46423-105">语法</span><span class="sxs-lookup"><span data-stu-id="46423-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46423-106">参数</span><span class="sxs-lookup"><span data-stu-id="46423-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="46423-107">[in] `params` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="46423-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="46423-108">[in]指向的指针`ULONG32`接收包含参数所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="46423-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="46423-109">[out]指向接收参数的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="46423-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46423-110">返回值</span><span class="sxs-lookup"><span data-stu-id="46423-110">Return Value</span></span>  
 <span data-ttu-id="46423-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="46423-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46423-112">惠?</span><span class="sxs-lookup"><span data-stu-id="46423-112">Requirements</span></span>  
 <span data-ttu-id="46423-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46423-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46423-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="46423-114">See Also</span></span>  
 [<span data-ttu-id="46423-115">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="46423-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
