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
ms.openlocfilehash: b8a3a74888a3caae03da6f88a003bd277939ae59
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615041"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="23cde-102">ISymUnmanagedReader::GetDocuments 方法</span><span class="sxs-lookup"><span data-stu-id="23cde-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="23cde-103">返回在符号存储区中定义的所有文档的数组。</span><span class="sxs-lookup"><span data-stu-id="23cde-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23cde-104">语法</span><span class="sxs-lookup"><span data-stu-id="23cde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23cde-105">参数</span><span class="sxs-lookup"><span data-stu-id="23cde-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="23cde-106">[in] `pDocs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="23cde-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="23cde-107">弄指向接收数组长度的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="23cde-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="23cde-108">弄指向接收文档数组的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="23cde-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23cde-109">返回值</span><span class="sxs-lookup"><span data-stu-id="23cde-109">Return Value</span></span>  
 <span data-ttu-id="23cde-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="23cde-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23cde-111">要求</span><span class="sxs-lookup"><span data-stu-id="23cde-111">Requirements</span></span>  
 <span data-ttu-id="23cde-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="23cde-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23cde-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23cde-113">See also</span></span>

- [<span data-ttu-id="23cde-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="23cde-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
