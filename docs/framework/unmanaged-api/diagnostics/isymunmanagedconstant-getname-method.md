---
title: ISymUnmanagedConstant::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 924feaeb91b42404461ad5d276c0cb77279d4dc4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449280"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="dbdfa-102">ISymUnmanagedConstant::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="dbdfa-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="dbdfa-103">获取常数的名称。</span><span class="sxs-lookup"><span data-stu-id="dbdfa-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbdfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbdfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbdfa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dbdfa-106">中`szName` 参数指向的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="dbdfa-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dbdfa-107">弄指向 `ULONG32` 的指针，该指针接收包含名称所需的缓冲区的大小（以字符数表示，包括 null 终止）。</span><span class="sxs-lookup"><span data-stu-id="dbdfa-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="dbdfa-108">弄存储名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="dbdfa-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbdfa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="dbdfa-109">Return Value</span></span>  
 <span data-ttu-id="dbdfa-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="dbdfa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbdfa-111">要求</span><span class="sxs-lookup"><span data-stu-id="dbdfa-111">Requirements</span></span>  
 <span data-ttu-id="dbdfa-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="dbdfa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdfa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbdfa-113">See also</span></span>

- [<span data-ttu-id="dbdfa-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="dbdfa-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="dbdfa-115">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="dbdfa-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="dbdfa-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="dbdfa-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
