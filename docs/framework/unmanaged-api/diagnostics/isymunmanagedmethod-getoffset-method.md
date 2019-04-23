---
title: ISymUnmanagedMethod::GetOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a42dc624d4de9cddebad287f6d90590f96b30272
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223649"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="8203d-102">ISymUnmanagedMethod::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="8203d-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="8203d-103">返回到文档中的给定位置中此方法相对应的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8203d-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8203d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8203d-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8203d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8203d-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="8203d-106">[in]指向为其请求偏移量的文档的指针。</span><span class="sxs-lookup"><span data-stu-id="8203d-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="8203d-107">[in]为其请求偏移量的文档行。</span><span class="sxs-lookup"><span data-stu-id="8203d-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="8203d-108">[in]为其请求偏移量的文档列。</span><span class="sxs-lookup"><span data-stu-id="8203d-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8203d-109">[out]一个指向`ULONG32`，它接收的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8203d-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8203d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8203d-110">Return Value</span></span>  
 <span data-ttu-id="8203d-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8203d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8203d-112">要求</span><span class="sxs-lookup"><span data-stu-id="8203d-112">Requirements</span></span>  
 <span data-ttu-id="8203d-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8203d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8203d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8203d-114">See also</span></span>

- [<span data-ttu-id="8203d-115">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="8203d-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
