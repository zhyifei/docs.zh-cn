---
title: "ISymUnmanagedWriter::SetSymAttribute 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90360d6fe5a1a95719a9bb09e5e0b6b2a70675a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="436d1-102">ISymUnmanagedWriter::SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="436d1-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="436d1-103">定义基于其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="436d1-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="436d1-104">这些属性保存在符号存储区，与元数据自定义特性不同。</span><span class="sxs-lookup"><span data-stu-id="436d1-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="436d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="436d1-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="436d1-106">参数</span><span class="sxs-lookup"><span data-stu-id="436d1-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="436d1-107">[in]正在为其定义的属性元数据标记。</span><span class="sxs-lookup"><span data-stu-id="436d1-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="436d1-108">[in]指向的指针`WCHAR`，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="436d1-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="436d1-109">[in]A `ULONG32` ，该值指示的大小`data`数组。</span><span class="sxs-lookup"><span data-stu-id="436d1-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="436d1-110">[in]特性值。</span><span class="sxs-lookup"><span data-stu-id="436d1-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="436d1-111">返回值</span><span class="sxs-lookup"><span data-stu-id="436d1-111">Return Value</span></span>  
 <span data-ttu-id="436d1-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="436d1-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="436d1-113">惠?</span><span class="sxs-lookup"><span data-stu-id="436d1-113">Requirements</span></span>  
 <span data-ttu-id="436d1-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="436d1-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436d1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="436d1-115">See Also</span></span>  
 [<span data-ttu-id="436d1-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="436d1-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
