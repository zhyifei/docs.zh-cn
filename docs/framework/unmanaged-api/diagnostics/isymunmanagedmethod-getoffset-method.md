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
ms.openlocfilehash: 358f3d3d7c231a2baa9d2c467935ba3a5867e36b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614469"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="eb72a-102">ISymUnmanagedMethod::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="eb72a-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="eb72a-103">返回此方法内的偏移量，该偏移量对应于文档中的给定位置。</span><span class="sxs-lookup"><span data-stu-id="eb72a-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb72a-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb72a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb72a-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb72a-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="eb72a-106">中指向为其请求偏移量的文档的指针。</span><span class="sxs-lookup"><span data-stu-id="eb72a-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="eb72a-107">中为其请求偏移量的文档行。</span><span class="sxs-lookup"><span data-stu-id="eb72a-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="eb72a-108">中为其请求偏移量的文档列。</span><span class="sxs-lookup"><span data-stu-id="eb72a-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="eb72a-109">弄指向 `ULONG32` 的指针，该指针接收偏移量。</span><span class="sxs-lookup"><span data-stu-id="eb72a-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb72a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="eb72a-110">Return Value</span></span>  
 <span data-ttu-id="eb72a-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="eb72a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb72a-112">要求</span><span class="sxs-lookup"><span data-stu-id="eb72a-112">Requirements</span></span>  
 <span data-ttu-id="eb72a-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="eb72a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb72a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb72a-114">See also</span></span>

- [<span data-ttu-id="eb72a-115">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="eb72a-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
