---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b59d85227f21bb230333456eda9130416563111
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180520"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="f5c4f-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 方法</span><span class="sxs-lookup"><span data-stu-id="f5c4f-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="f5c4f-103">获取符号搜索信息的计数。</span><span class="sxs-lookup"><span data-stu-id="f5c4f-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5c4f-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5c4f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5c4f-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="f5c4f-106">] out] 一个指向`ULONG32`接收包含搜索信息所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="f5c4f-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5c4f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f5c4f-107">Return Value</span></span>  
 <span data-ttu-id="f5c4f-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f5c4f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c4f-109">要求</span><span class="sxs-lookup"><span data-stu-id="f5c4f-109">Requirements</span></span>  
 <span data-ttu-id="f5c4f-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5c4f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c4f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5c4f-111">See also</span></span>

- [<span data-ttu-id="f5c4f-112">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f5c4f-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
