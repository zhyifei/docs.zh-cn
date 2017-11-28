---
title: "ISymUnmanagedReader::GetVariables 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9ef176b3863b2c1c9422bfd0aeb8814401a22d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="7b1df-102">ISymUnmanagedReader::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="7b1df-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="7b1df-103">返回一个非本地变量，给定的父级和名称。</span><span class="sxs-lookup"><span data-stu-id="7b1df-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b1df-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b1df-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b1df-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b1df-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="7b1df-106">[in]变量的父级。</span><span class="sxs-lookup"><span data-stu-id="7b1df-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="7b1df-107">[in] `pVars` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="7b1df-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="7b1df-108">[out]指向接收的变量中返回数的变量的指针`pVars`。</span><span class="sxs-lookup"><span data-stu-id="7b1df-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="7b1df-109">[out]指向接收这些变量的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="7b1df-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b1df-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7b1df-110">Return Value</span></span>  
 <span data-ttu-id="7b1df-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="7b1df-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b1df-112">要求</span><span class="sxs-lookup"><span data-stu-id="7b1df-112">Requirements</span></span>  
 <span data-ttu-id="7b1df-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b1df-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1df-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b1df-114">See Also</span></span>  
 [<span data-ttu-id="7b1df-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="7b1df-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
