---
title: "ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f82cf213e9bcc83055cfaa42b9acab9d395d405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="c8742-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="c8742-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="c8742-103">返回的数组的方法，其中每个包含文档中的给定位置处的断点。</span><span class="sxs-lookup"><span data-stu-id="c8742-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8742-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8742-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8742-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8742-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="c8742-106">[in]指定的文档。</span><span class="sxs-lookup"><span data-stu-id="c8742-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="c8742-107">[in]指定的文档的行。</span><span class="sxs-lookup"><span data-stu-id="c8742-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="c8742-108">[in]指定的文档的列。</span><span class="sxs-lookup"><span data-stu-id="c8742-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="c8742-109">[in] `pRetVal` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="c8742-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="c8742-110">[out]指向接收中返回的元素数的变量的指针`pRetVal`数组。</span><span class="sxs-lookup"><span data-stu-id="c8742-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c8742-111">[out]一个指针，其中每个指向数组[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)对象，表示包含该断点的方法。</span><span class="sxs-lookup"><span data-stu-id="c8742-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8742-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c8742-112">Return Value</span></span>  
 <span data-ttu-id="c8742-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c8742-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8742-114">要求</span><span class="sxs-lookup"><span data-stu-id="c8742-114">Requirements</span></span>  
 <span data-ttu-id="c8742-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8742-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8742-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8742-116">See Also</span></span>  
 [<span data-ttu-id="c8742-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="c8742-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
