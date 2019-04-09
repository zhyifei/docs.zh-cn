---
title: ISymUnmanagedVariable::GetSignature 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3cc616246812bb9643388d8ad57cf84bc387b55e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136410"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="efb92-102">ISymUnmanagedVariable::GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="efb92-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="efb92-103">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="efb92-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb92-104">语法</span><span class="sxs-lookup"><span data-stu-id="efb92-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb92-105">参数</span><span class="sxs-lookup"><span data-stu-id="efb92-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="efb92-106">[in]指向缓冲区的长度`sig`参数。</span><span class="sxs-lookup"><span data-stu-id="efb92-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="efb92-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含该签名所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="efb92-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="efb92-108">[out]存储签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="efb92-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efb92-109">返回值</span><span class="sxs-lookup"><span data-stu-id="efb92-109">Return Value</span></span>  
 <span data-ttu-id="efb92-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="efb92-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb92-111">要求</span><span class="sxs-lookup"><span data-stu-id="efb92-111">Requirements</span></span>  
 <span data-ttu-id="efb92-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="efb92-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb92-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="efb92-113">See also</span></span>

- [<span data-ttu-id="efb92-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="efb92-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
