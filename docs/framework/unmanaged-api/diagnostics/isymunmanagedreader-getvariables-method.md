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
ms.openlocfilehash: 637e1aed003e211654141ab397c9c0b4724753c2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615483"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="db1e5-102">ISymUnmanagedReader::GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="db1e5-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="db1e5-103">在给定父和名称的情况下，返回非局部变量。</span><span class="sxs-lookup"><span data-stu-id="db1e5-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="db1e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="db1e5-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="db1e5-106">中变量的父级。</span><span class="sxs-lookup"><span data-stu-id="db1e5-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="db1e5-107">[in] `pVars` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="db1e5-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="db1e5-108">弄指向一个变量的指针，该变量接收返回的变量数 `pVars` 。</span><span class="sxs-lookup"><span data-stu-id="db1e5-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="db1e5-109">弄指向接收变量的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="db1e5-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db1e5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="db1e5-110">Return Value</span></span>  
 <span data-ttu-id="db1e5-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="db1e5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1e5-112">要求</span><span class="sxs-lookup"><span data-stu-id="db1e5-112">Requirements</span></span>  
 <span data-ttu-id="db1e5-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="db1e5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1e5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db1e5-114">See also</span></span>

- [<span data-ttu-id="db1e5-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="db1e5-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
