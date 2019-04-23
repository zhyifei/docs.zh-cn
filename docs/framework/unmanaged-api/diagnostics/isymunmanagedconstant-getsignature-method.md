---
title: ISymUnmanagedConstant::GetSignature 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab1282109d7241c2599f8ca029fc79e4a3135209
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170984"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="33f28-102">ISymUnmanagedConstant::GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="33f28-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="33f28-103">获取常量的签名。</span><span class="sxs-lookup"><span data-stu-id="33f28-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f28-104">语法</span><span class="sxs-lookup"><span data-stu-id="33f28-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33f28-105">参数</span><span class="sxs-lookup"><span data-stu-id="33f28-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="33f28-106">[in]缓冲区的长度的`pcSig`参数指向。</span><span class="sxs-lookup"><span data-stu-id="33f28-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="33f28-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含该签名所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="33f28-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="33f28-108">[out]存储签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="33f28-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33f28-109">返回值</span><span class="sxs-lookup"><span data-stu-id="33f28-109">Return Value</span></span>  
 <span data-ttu-id="33f28-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="33f28-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33f28-111">要求</span><span class="sxs-lookup"><span data-stu-id="33f28-111">Requirements</span></span>  
 <span data-ttu-id="33f28-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33f28-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f28-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="33f28-113">See also</span></span>

- [<span data-ttu-id="33f28-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="33f28-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="33f28-115">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="33f28-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="33f28-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="33f28-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
