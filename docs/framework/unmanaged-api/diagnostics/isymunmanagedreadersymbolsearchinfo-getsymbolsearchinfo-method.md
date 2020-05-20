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
ms.openlocfilehash: 2b5a42c89e0e3efed61b1b471c227e0df85a51aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614898"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="9aa70-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 方法</span><span class="sxs-lookup"><span data-stu-id="9aa70-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="9aa70-103">获取符号搜索信息。</span><span class="sxs-lookup"><span data-stu-id="9aa70-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa70-104">语法</span><span class="sxs-lookup"><span data-stu-id="9aa70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aa70-105">参数</span><span class="sxs-lookup"><span data-stu-id="9aa70-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="9aa70-106">中`ULONG32`指示的大小的 `rgpSearchInfo` 。</span><span class="sxs-lookup"><span data-stu-id="9aa70-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="9aa70-107">弄指向的指针 `ULONG32` ，该指针接收包含搜索信息所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="9aa70-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="9aa70-108">弄设置为返回的[ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="9aa70-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aa70-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9aa70-109">Return Value</span></span>  
 <span data-ttu-id="9aa70-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="9aa70-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aa70-111">要求</span><span class="sxs-lookup"><span data-stu-id="9aa70-111">Requirements</span></span>  
 <span data-ttu-id="9aa70-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="9aa70-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa70-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa70-113">See also</span></span>

- [<span data-ttu-id="9aa70-114">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9aa70-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
