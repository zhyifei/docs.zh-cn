---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f87399b1124870101531f7115d0da211e646562f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670140"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="96f21-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="96f21-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="96f21-103">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="96f21-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f21-104">语法</span><span class="sxs-lookup"><span data-stu-id="96f21-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96f21-105">参数</span><span class="sxs-lookup"><span data-stu-id="96f21-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="96f21-106">[out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含搜索路径的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="96f21-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96f21-107">返回值</span><span class="sxs-lookup"><span data-stu-id="96f21-107">Return Value</span></span>  
 <span data-ttu-id="96f21-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="96f21-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f21-109">要求</span><span class="sxs-lookup"><span data-stu-id="96f21-109">Requirements</span></span>  
 <span data-ttu-id="96f21-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="96f21-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f21-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="96f21-111">See also</span></span>
- [<span data-ttu-id="96f21-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="96f21-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
