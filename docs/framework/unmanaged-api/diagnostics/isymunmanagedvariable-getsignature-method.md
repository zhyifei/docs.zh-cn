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
ms.openlocfilehash: abd4bb00f5c1e703740462f1709407616ac8a8e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778238"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="bc1d4-102">ISymUnmanagedVariable::GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="bc1d4-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="bc1d4-103">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc1d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc1d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc1d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc1d4-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="bc1d4-106">[in]指向缓冲区的长度`sig`参数。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="bc1d4-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，包含该签名所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="bc1d4-108">[out]存储签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc1d4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bc1d4-109">Return Value</span></span>  
 <span data-ttu-id="bc1d4-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bc1d4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc1d4-111">要求</span><span class="sxs-lookup"><span data-stu-id="bc1d4-111">Requirements</span></span>  
 <span data-ttu-id="bc1d4-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bc1d4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1d4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc1d4-113">See also</span></span>

- [<span data-ttu-id="bc1d4-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="bc1d4-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
