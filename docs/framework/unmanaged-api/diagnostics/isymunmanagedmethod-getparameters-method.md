---
title: ISymUnmanagedMethod::GetParameters 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a757e3b28a94c96e28a5bab736a6820a83617a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101199"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="a0318-102">ISymUnmanagedMethod::GetParameters 方法</span><span class="sxs-lookup"><span data-stu-id="a0318-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="a0318-103">获取此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="a0318-103">Gets the parameters for this method.</span></span> <span data-ttu-id="a0318-104">参数的方法签名中定义的顺序返回。</span><span class="sxs-lookup"><span data-stu-id="a0318-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0318-105">语法</span><span class="sxs-lookup"><span data-stu-id="a0318-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0318-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0318-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="a0318-107">[in] `params` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="a0318-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="a0318-108">[in]一个指向`ULONG32`接收包含参数所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="a0318-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="a0318-109">[out]指向接收参数的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="a0318-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0318-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a0318-110">Return Value</span></span>  
 <span data-ttu-id="a0318-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="a0318-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0318-112">要求</span><span class="sxs-lookup"><span data-stu-id="a0318-112">Requirements</span></span>  
 <span data-ttu-id="a0318-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0318-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0318-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0318-114">See also</span></span>

- [<span data-ttu-id="a0318-115">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="a0318-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
