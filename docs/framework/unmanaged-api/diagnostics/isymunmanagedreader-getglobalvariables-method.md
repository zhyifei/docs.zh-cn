---
title: ISymUnmanagedReader::GetGlobalVariables 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986383"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="5d95f-102">ISymUnmanagedReader::GetGlobalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="5d95f-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="5d95f-103">返回所有全局变量。</span><span class="sxs-lookup"><span data-stu-id="5d95f-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d95f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d95f-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d95f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d95f-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="5d95f-106">[in]指向缓冲区的长度`pcVars`。</span><span class="sxs-lookup"><span data-stu-id="5d95f-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="5d95f-107">[out]一个指向`ULONG32`接收包含变量所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="5d95f-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="5d95f-108">[out]包含变量的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5d95f-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d95f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5d95f-109">Return Value</span></span>  
 <span data-ttu-id="5d95f-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="5d95f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d95f-111">要求</span><span class="sxs-lookup"><span data-stu-id="5d95f-111">Requirements</span></span>  
 <span data-ttu-id="5d95f-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d95f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d95f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d95f-113">See also</span></span>

- [<span data-ttu-id="5d95f-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="5d95f-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
