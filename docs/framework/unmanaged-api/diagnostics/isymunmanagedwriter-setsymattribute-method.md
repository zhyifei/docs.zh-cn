---
title: ISymUnmanagedWriter::SetSymAttribute 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ee3e96a25a224fb5b025e22fa43169a64f6c0d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501664"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="068dd-102">ISymUnmanagedWriter::SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="068dd-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="068dd-103">定义根据其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="068dd-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="068dd-104">这些属性保存在符号存储区，与不同的元数据自定义属性。</span><span class="sxs-lookup"><span data-stu-id="068dd-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="068dd-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="068dd-106">参数</span><span class="sxs-lookup"><span data-stu-id="068dd-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="068dd-107">[in]为其定义的属性元数据标记。</span><span class="sxs-lookup"><span data-stu-id="068dd-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="068dd-108">[in]一个指向`WCHAR`，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="068dd-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="068dd-109">[in]一个`ULONG32`指示的大小`data`数组。</span><span class="sxs-lookup"><span data-stu-id="068dd-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="068dd-110">[in]属性值。</span><span class="sxs-lookup"><span data-stu-id="068dd-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="068dd-111">返回值</span><span class="sxs-lookup"><span data-stu-id="068dd-111">Return Value</span></span>  
 <span data-ttu-id="068dd-112">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="068dd-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068dd-113">要求</span><span class="sxs-lookup"><span data-stu-id="068dd-113">Requirements</span></span>  
 <span data-ttu-id="068dd-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="068dd-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068dd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="068dd-115">See also</span></span>
- [<span data-ttu-id="068dd-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="068dd-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
