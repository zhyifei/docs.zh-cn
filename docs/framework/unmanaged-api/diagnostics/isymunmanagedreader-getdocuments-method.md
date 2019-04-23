---
title: ISymUnmanagedReader::GetDocuments 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efcf5b6673fbdc37fad99d082f91ab3077abbea9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130593"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="f5650-102">ISymUnmanagedReader::GetDocuments 方法</span><span class="sxs-lookup"><span data-stu-id="f5650-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="f5650-103">返回一组符号存储区中定义的所有文档。</span><span class="sxs-lookup"><span data-stu-id="f5650-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5650-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5650-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5650-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5650-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="f5650-106">[in] `pDocs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f5650-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="f5650-107">[out]指向一个变量来接收数组长度的指针。</span><span class="sxs-lookup"><span data-stu-id="f5650-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="f5650-108">[out]指向一个变量来接收的文档数组的指针。</span><span class="sxs-lookup"><span data-stu-id="f5650-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5650-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f5650-109">Return Value</span></span>  
 <span data-ttu-id="f5650-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f5650-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5650-111">要求</span><span class="sxs-lookup"><span data-stu-id="f5650-111">Requirements</span></span>  
 <span data-ttu-id="f5650-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5650-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5650-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5650-113">See also</span></span>

- [<span data-ttu-id="f5650-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="f5650-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
