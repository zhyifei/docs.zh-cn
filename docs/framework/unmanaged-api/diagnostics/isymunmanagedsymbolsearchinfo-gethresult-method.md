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
ms.openlocfilehash: 1534955c1f7cfd37732a08b0b33cda5bff8a8aab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113017"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="722d5-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 方法</span><span class="sxs-lookup"><span data-stu-id="722d5-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="722d5-103">获取 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="722d5-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="722d5-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="722d5-105">参数</span><span class="sxs-lookup"><span data-stu-id="722d5-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="722d5-106">[out]指向 HRESULT 的指针。</span><span class="sxs-lookup"><span data-stu-id="722d5-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="722d5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="722d5-107">Return Value</span></span>  
 <span data-ttu-id="722d5-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="722d5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="722d5-109">要求</span><span class="sxs-lookup"><span data-stu-id="722d5-109">Requirements</span></span>  
 <span data-ttu-id="722d5-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="722d5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="722d5-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="722d5-111">See also</span></span>

- [<span data-ttu-id="722d5-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="722d5-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
