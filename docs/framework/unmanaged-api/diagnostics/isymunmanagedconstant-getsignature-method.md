---
title: "ISymUnmanagedConstant::GetSignature 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10bdf7b8b83b56ff856d966d2764ed04e06090aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="8d3cd-102">ISymUnmanagedConstant::GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="8d3cd-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="8d3cd-103">获取该常量的签名。</span><span class="sxs-lookup"><span data-stu-id="8d3cd-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d3cd-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d3cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d3cd-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="8d3cd-106">[in]缓冲区的长度，`pcSig`参数指向。</span><span class="sxs-lookup"><span data-stu-id="8d3cd-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="8d3cd-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含签名所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8d3cd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="8d3cd-108">[out]存储签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8d3cd-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d3cd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8d3cd-109">Return Value</span></span>  
 <span data-ttu-id="8d3cd-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8d3cd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3cd-111">惠?</span><span class="sxs-lookup"><span data-stu-id="8d3cd-111">Requirements</span></span>  
 <span data-ttu-id="8d3cd-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8d3cd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3cd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d3cd-113">See Also</span></span>  
 [<span data-ttu-id="8d3cd-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="8d3cd-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="8d3cd-115">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="8d3cd-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="8d3cd-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="8d3cd-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
