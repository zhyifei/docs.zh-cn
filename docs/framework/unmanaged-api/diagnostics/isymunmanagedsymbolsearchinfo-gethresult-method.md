---
title: "ISymUnmanagedSymbolSearchInfo::GetHRESULT 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42f2e0053a83d4ef7414791626ec204671429a3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="7f798-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 方法</span><span class="sxs-lookup"><span data-stu-id="7f798-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="7f798-103">获取 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="7f798-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f798-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f798-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f798-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f798-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="7f798-106">[out]指向 HRESULT 的指针。</span><span class="sxs-lookup"><span data-stu-id="7f798-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f798-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7f798-107">Return Value</span></span>  
 <span data-ttu-id="7f798-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7f798-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f798-109">要求</span><span class="sxs-lookup"><span data-stu-id="7f798-109">Requirements</span></span>  
 <span data-ttu-id="7f798-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7f798-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f798-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f798-111">See Also</span></span>  
 [<span data-ttu-id="7f798-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7f798-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
