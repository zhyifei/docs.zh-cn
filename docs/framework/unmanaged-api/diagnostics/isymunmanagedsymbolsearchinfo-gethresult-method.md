---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd24289f7e670684effa553f930af9aec92e5730
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469595"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="c0305-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 方法</span><span class="sxs-lookup"><span data-stu-id="c0305-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="c0305-103">获取 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="c0305-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0305-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0305-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0305-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0305-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="c0305-106">[out]指向 HRESULT 的指针。</span><span class="sxs-lookup"><span data-stu-id="c0305-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0305-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c0305-107">Return Value</span></span>  
 <span data-ttu-id="c0305-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c0305-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0305-109">要求</span><span class="sxs-lookup"><span data-stu-id="c0305-109">Requirements</span></span>  
 <span data-ttu-id="c0305-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c0305-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0305-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0305-111">See also</span></span>
- [<span data-ttu-id="c0305-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c0305-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
