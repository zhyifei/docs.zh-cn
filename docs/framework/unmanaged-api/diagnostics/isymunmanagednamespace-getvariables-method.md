---
title: ISymUnmanagedNamespace::GetVariables 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a5eb01a3e354b4360bea59af1e63ffeb0576aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730108"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="92ab1-102">ISymUnmanagedNamespace::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="92ab1-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="92ab1-103">返回在此命名空间中的全局范围内定义的所有变量。</span><span class="sxs-lookup"><span data-stu-id="92ab1-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ab1-104">语法</span><span class="sxs-lookup"><span data-stu-id="92ab1-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92ab1-105">参数</span><span class="sxs-lookup"><span data-stu-id="92ab1-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="92ab1-106">[in]一个`ULONG32`指示的大小`pVars`数组。</span><span class="sxs-lookup"><span data-stu-id="92ab1-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="92ab1-107">[out]一个指向`ULONG32`接收包含命名空间所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="92ab1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="92ab1-108">[out]指向包含的命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="92ab1-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92ab1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="92ab1-109">Return Value</span></span>  
 <span data-ttu-id="92ab1-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="92ab1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ab1-111">要求</span><span class="sxs-lookup"><span data-stu-id="92ab1-111">Requirements</span></span>  
 <span data-ttu-id="92ab1-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92ab1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ab1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="92ab1-113">See also</span></span>
- [<span data-ttu-id="92ab1-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="92ab1-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
