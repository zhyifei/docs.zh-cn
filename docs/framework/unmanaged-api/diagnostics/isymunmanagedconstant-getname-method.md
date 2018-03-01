---
title: "ISymUnmanagedConstant::GetName 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d312329a2e59376c94937cf3d9bc08a8e6e0e862
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="592fd-102">ISymUnmanagedConstant::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="592fd-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="592fd-103">获取的常数的名称。</span><span class="sxs-lookup"><span data-stu-id="592fd-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="592fd-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="592fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="592fd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="592fd-106">[in]缓冲区的长度，`szName`参数指向。</span><span class="sxs-lookup"><span data-stu-id="592fd-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="592fd-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含文件的名称，包括 null 终止所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="592fd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="592fd-108">[out]存储的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="592fd-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="592fd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="592fd-109">Return Value</span></span>  
 <span data-ttu-id="592fd-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="592fd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="592fd-111">惠?</span><span class="sxs-lookup"><span data-stu-id="592fd-111">Requirements</span></span>  
 <span data-ttu-id="592fd-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="592fd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592fd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="592fd-113">See Also</span></span>  
 [<span data-ttu-id="592fd-114">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="592fd-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="592fd-115">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="592fd-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)  
 [<span data-ttu-id="592fd-116">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="592fd-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
