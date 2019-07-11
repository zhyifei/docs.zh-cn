---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1935b831902e975616557f512789c339baf49c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776972"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="086c2-102">ISymUnmanagedReader::GetMethodFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="086c2-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="086c2-103">返回包含在文档中的给定位置处的断点的方法。</span><span class="sxs-lookup"><span data-stu-id="086c2-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="086c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="086c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="086c2-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="086c2-106">[in]指定的文档。</span><span class="sxs-lookup"><span data-stu-id="086c2-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="086c2-107">[in]指定文档的行。</span><span class="sxs-lookup"><span data-stu-id="086c2-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="086c2-108">[in]指定文档的列。</span><span class="sxs-lookup"><span data-stu-id="086c2-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="086c2-109">[out]指向的地址的指针[ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)对象，表示包含断点的方法。</span><span class="sxs-lookup"><span data-stu-id="086c2-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="086c2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="086c2-110">Return Value</span></span>  
 <span data-ttu-id="086c2-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="086c2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="086c2-112">要求</span><span class="sxs-lookup"><span data-stu-id="086c2-112">Requirements</span></span>  
 <span data-ttu-id="086c2-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="086c2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086c2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="086c2-114">See also</span></span>

- [<span data-ttu-id="086c2-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="086c2-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
