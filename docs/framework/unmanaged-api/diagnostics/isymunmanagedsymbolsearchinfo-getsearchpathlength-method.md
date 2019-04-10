---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170607"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="7df3d-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 方法</span><span class="sxs-lookup"><span data-stu-id="7df3d-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="7df3d-103">获取搜索路径长度。</span><span class="sxs-lookup"><span data-stu-id="7df3d-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7df3d-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7df3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7df3d-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="7df3d-106">[out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含搜索路径长度的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7df3d-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7df3d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7df3d-107">Return Value</span></span>  
 <span data-ttu-id="7df3d-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7df3d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df3d-109">要求</span><span class="sxs-lookup"><span data-stu-id="7df3d-109">Requirements</span></span>  
 <span data-ttu-id="7df3d-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7df3d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df3d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df3d-111">See also</span></span>

- [<span data-ttu-id="7df3d-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7df3d-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
