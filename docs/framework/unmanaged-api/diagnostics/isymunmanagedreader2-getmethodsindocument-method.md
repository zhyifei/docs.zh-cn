---
title: ISymUnmanagedReader2::GetMethodsInDocument 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 762649e260817c43291de416d2f1a92a8f03afb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427364"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="976dc-102">ISymUnmanagedReader2::GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="976dc-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="976dc-103">获取每个方法，提供的文档中包含行信息。</span><span class="sxs-lookup"><span data-stu-id="976dc-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="976dc-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="976dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="976dc-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="976dc-106">[in]指向文档的指针。</span><span class="sxs-lookup"><span data-stu-id="976dc-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="976dc-107">[in]A `ULONG32` ，该值指示的大小`pRetVal`数组。</span><span class="sxs-lookup"><span data-stu-id="976dc-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="976dc-108">[out]指向的指针`ULONG32`接收包含方法所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="976dc-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="976dc-109">[out]指向接收方法的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="976dc-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="976dc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="976dc-110">Return Value</span></span>  
 <span data-ttu-id="976dc-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="976dc-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="976dc-112">要求</span><span class="sxs-lookup"><span data-stu-id="976dc-112">Requirements</span></span>  
 <span data-ttu-id="976dc-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="976dc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976dc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="976dc-114">See Also</span></span>  
 [<span data-ttu-id="976dc-115">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="976dc-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
