---
title: "ISymUnmanagedBinder::GetReaderFromStream 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 96bd12b69b84537415ddf2e0ae992ec179f32493
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="3e3af-102">ISymUnmanagedBinder::GetReaderFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="3e3af-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="3e3af-103">指定元数据接口和包含符号存储区的流，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 结构，它将读取调试符号从给定的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="3e3af-103">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e3af-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e3af-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e3af-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e3af-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3e3af-106">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="3e3af-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="3e3af-107">[in]指向包含符号存储区的流的指针。</span><span class="sxs-lookup"><span data-stu-id="3e3af-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3e3af-108">[out]一个指针，它设置为返回 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 接口。</span><span class="sxs-lookup"><span data-stu-id="3e3af-108">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e3af-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3e3af-109">Return Value</span></span>  
 <span data-ttu-id="3e3af-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="3e3af-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e3af-111">要求</span><span class="sxs-lookup"><span data-stu-id="3e3af-111">Requirements</span></span>  
 <span data-ttu-id="3e3af-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3e3af-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3af-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e3af-113">See Also</span></span>  
 [<span data-ttu-id="3e3af-114">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="3e3af-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
