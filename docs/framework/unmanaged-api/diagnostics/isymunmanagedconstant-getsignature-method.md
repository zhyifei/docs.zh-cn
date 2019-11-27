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
ms.openlocfilehash: 401dfbea0da309db24f3052f462daa66e8bbef4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449264"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="2a083-102">ISymUnmanagedConstant::GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="2a083-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="2a083-103">获取常量的签名。</span><span class="sxs-lookup"><span data-stu-id="2a083-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a083-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a083-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a083-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a083-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="2a083-106">中`pcSig` 参数指向的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="2a083-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="2a083-107">弄指向 `ULONG32` 的指针，该指针接收包含签名所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="2a083-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="2a083-108">弄存储签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2a083-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a083-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2a083-109">Return Value</span></span>  
 <span data-ttu-id="2a083-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2a083-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a083-111">要求</span><span class="sxs-lookup"><span data-stu-id="2a083-111">Requirements</span></span>  
 <span data-ttu-id="2a083-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2a083-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a083-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a083-113">See also</span></span>

- [<span data-ttu-id="2a083-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="2a083-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="2a083-115">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="2a083-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="2a083-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="2a083-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
