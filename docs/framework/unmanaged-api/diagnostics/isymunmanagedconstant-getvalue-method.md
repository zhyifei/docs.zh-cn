---
title: ISymUnmanagedConstant::GetValue 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204661"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="32e85-102">ISymUnmanagedConstant::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="32e85-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="32e85-103">获取常量的值。</span><span class="sxs-lookup"><span data-stu-id="32e85-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e85-104">语法</span><span class="sxs-lookup"><span data-stu-id="32e85-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e85-105">参数</span><span class="sxs-lookup"><span data-stu-id="32e85-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="32e85-106">[out]指向一个变量来接收值的指针。</span><span class="sxs-lookup"><span data-stu-id="32e85-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32e85-107">返回值</span><span class="sxs-lookup"><span data-stu-id="32e85-107">Return Value</span></span>  
 <span data-ttu-id="32e85-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="32e85-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e85-109">要求</span><span class="sxs-lookup"><span data-stu-id="32e85-109">Requirements</span></span>  
 <span data-ttu-id="32e85-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32e85-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e85-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="32e85-111">See also</span></span>

- [<span data-ttu-id="32e85-112">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="32e85-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="32e85-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="32e85-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="32e85-114">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="32e85-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
