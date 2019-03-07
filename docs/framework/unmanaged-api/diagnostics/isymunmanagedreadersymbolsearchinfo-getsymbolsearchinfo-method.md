---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb290314328023c95d0028dd90687b1a6926ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501066"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="56de3-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="56de3-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="56de3-103">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="56de3-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56de3-104">语法</span><span class="sxs-lookup"><span data-stu-id="56de3-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56de3-105">参数</span><span class="sxs-lookup"><span data-stu-id="56de3-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="56de3-106">[in]一个`ULONG32`指示的大小`rgpSearchInfo`。</span><span class="sxs-lookup"><span data-stu-id="56de3-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="56de3-107">[out]一个指向`ULONG32`接收包含搜索信息所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="56de3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="56de3-108">[out]一个指针，它设置为返回[ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="56de3-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56de3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="56de3-109">Return Value</span></span>  
 <span data-ttu-id="56de3-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="56de3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56de3-111">要求</span><span class="sxs-lookup"><span data-stu-id="56de3-111">Requirements</span></span>  
 <span data-ttu-id="56de3-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="56de3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56de3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="56de3-113">See also</span></span>
- [<span data-ttu-id="56de3-114">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="56de3-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
