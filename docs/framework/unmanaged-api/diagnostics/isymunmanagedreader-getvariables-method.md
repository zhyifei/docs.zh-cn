---
title: ISymUnmanagedReader::GetVariables 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 4590d2734ea89bc1bc8a30db1c7ecac5effafd7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429757"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="fcf32-102">ISymUnmanagedReader::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="fcf32-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="fcf32-103">在给定父和名称的情况下，返回非局部变量。</span><span class="sxs-lookup"><span data-stu-id="fcf32-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf32-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcf32-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf32-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcf32-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="fcf32-106">中变量的父级。</span><span class="sxs-lookup"><span data-stu-id="fcf32-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="fcf32-107">[in] `pVars` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="fcf32-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="fcf32-108">弄指向变量的指针，该变量接收 `pVars`中返回的变量数。</span><span class="sxs-lookup"><span data-stu-id="fcf32-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="fcf32-109">弄指向接收变量的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="fcf32-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcf32-110">返回值</span><span class="sxs-lookup"><span data-stu-id="fcf32-110">Return Value</span></span>  
 <span data-ttu-id="fcf32-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fcf32-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf32-112">要求</span><span class="sxs-lookup"><span data-stu-id="fcf32-112">Requirements</span></span>  
 <span data-ttu-id="fcf32-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fcf32-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf32-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcf32-114">See also</span></span>

- [<span data-ttu-id="fcf32-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="fcf32-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
