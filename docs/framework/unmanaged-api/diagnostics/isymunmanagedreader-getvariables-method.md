---
title: "ISymUnmanagedReader::GetVariables 方法"
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
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86a0f8ed0a73661b80a9a196682e9539a3b97141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="8b2ff-102">ISymUnmanagedReader::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="8b2ff-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="8b2ff-103">返回一个非本地变量，给定的父级和名称。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b2ff-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b2ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b2ff-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="8b2ff-106">[in]变量的父级。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="8b2ff-107">[in] `pVars` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="8b2ff-108">[out]指向接收的变量中返回数的变量的指针`pVars`。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="8b2ff-109">[out]指向接收这些变量的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b2ff-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8b2ff-110">Return Value</span></span>  
 <span data-ttu-id="8b2ff-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="8b2ff-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2ff-112">惠?</span><span class="sxs-lookup"><span data-stu-id="8b2ff-112">Requirements</span></span>  
 <span data-ttu-id="8b2ff-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8b2ff-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2ff-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b2ff-114">See Also</span></span>  
 [<span data-ttu-id="8b2ff-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="8b2ff-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
