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
ms.openlocfilehash: 402b5b4bc9734be59ff342a4f86f2c4a1ed23b5f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446408"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="454c4-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="454c4-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="454c4-103">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="454c4-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="454c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="454c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="454c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="454c4-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="454c4-106">中一个 `ULONG32`，指示 `rgpSearchInfo`的大小。</span><span class="sxs-lookup"><span data-stu-id="454c4-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="454c4-107">弄指向 `ULONG32` 的指针，该指针接收包含搜索信息所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="454c4-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="454c4-108">弄设置为返回的[ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="454c4-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="454c4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="454c4-109">Return Value</span></span>  
 <span data-ttu-id="454c4-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="454c4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="454c4-111">要求</span><span class="sxs-lookup"><span data-stu-id="454c4-111">Requirements</span></span>  
 <span data-ttu-id="454c4-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="454c4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454c4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="454c4-113">See also</span></span>

- [<span data-ttu-id="454c4-114">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="454c4-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
