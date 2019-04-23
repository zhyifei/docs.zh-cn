---
title: ISymUnmanagedBinder::GetReaderFromStream 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21e147860c6859ea23409de31fed972c4f2bb432
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220911"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="fc945-102">ISymUnmanagedBinder::GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="fc945-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="fc945-103">给定元数据接口并包含符号存储区的流，返回的正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)从给定的符号存储区的结构，它将读取调试符号。</span><span class="sxs-lookup"><span data-stu-id="fc945-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc945-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc945-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc945-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc945-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="fc945-106">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="fc945-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="fc945-107">[in]指向包含符号存储区的流的指针。</span><span class="sxs-lookup"><span data-stu-id="fc945-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc945-108">[out]一个指针，它设置为返回[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="fc945-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc945-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fc945-109">Return Value</span></span>  
 <span data-ttu-id="fc945-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fc945-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc945-111">要求</span><span class="sxs-lookup"><span data-stu-id="fc945-111">Requirements</span></span>  
 <span data-ttu-id="fc945-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc945-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc945-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc945-113">See also</span></span>

- [<span data-ttu-id="fc945-114">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="fc945-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
