---
title: "ISymUnmanagedReader2::GetSymAttributePreRemap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75608d89b6fd34570166718de824150b0621c84e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="5af45-102">ISymUnmanagedReader2::GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="5af45-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="5af45-103">获取基于其名称的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="5af45-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="5af45-104">与不同的元数据自定义特性，这些属性保存在符号存储区中。</span><span class="sxs-lookup"><span data-stu-id="5af45-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af45-105">语法</span><span class="sxs-lookup"><span data-stu-id="5af45-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5af45-106">参数</span><span class="sxs-lookup"><span data-stu-id="5af45-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="5af45-107">[in]父元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5af45-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="5af45-108">[in]指向的指针`WCHAR`包含的名称。</span><span class="sxs-lookup"><span data-stu-id="5af45-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="5af45-109">[in]A `ULONG32` ，该值指示的大小`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="5af45-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="5af45-110">[out]指向的指针`ULONG32`接收包含属性字节所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="5af45-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5af45-111">[out]指向接收属性字节的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="5af45-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5af45-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5af45-112">Return Value</span></span>  
 <span data-ttu-id="5af45-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="5af45-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af45-114">要求</span><span class="sxs-lookup"><span data-stu-id="5af45-114">Requirements</span></span>  
 <span data-ttu-id="5af45-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5af45-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af45-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5af45-116">See Also</span></span>  
 [<span data-ttu-id="5af45-117">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="5af45-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
