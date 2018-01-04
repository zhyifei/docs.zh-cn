---
title: "ISymUnmanagedReader::GetSymAttribute 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9795d5c7937f3c66c799665ba0e07e70c2be0b66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="5df6e-102">ISymUnmanagedReader::GetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="5df6e-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="5df6e-103">获取基于其名称的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="5df6e-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="5df6e-104">与不同的元数据自定义特性，这些自定义属性保存在符号存储区中。</span><span class="sxs-lookup"><span data-stu-id="5df6e-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df6e-105">语法</span><span class="sxs-lookup"><span data-stu-id="5df6e-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5df6e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5df6e-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="5df6e-107">[in]为其请求属性的对象元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5df6e-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="5df6e-108">[in]指示要检索的属性的变量指向的指针。</span><span class="sxs-lookup"><span data-stu-id="5df6e-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="5df6e-109">[in] `buffer` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="5df6e-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="5df6e-110">[out]指向接收的属性数据的长度的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="5df6e-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5df6e-111">[out]指向接收属性数据的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="5df6e-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5df6e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5df6e-112">Return Value</span></span>  
 <span data-ttu-id="5df6e-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码...</span><span class="sxs-lookup"><span data-stu-id="5df6e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5df6e-114">惠?</span><span class="sxs-lookup"><span data-stu-id="5df6e-114">Requirements</span></span>  
 <span data-ttu-id="5df6e-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5df6e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df6e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5df6e-116">See Also</span></span>  
 [<span data-ttu-id="5df6e-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="5df6e-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
