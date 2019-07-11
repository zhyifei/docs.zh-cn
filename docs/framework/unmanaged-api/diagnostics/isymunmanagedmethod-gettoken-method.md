---
title: ISymUnmanagedMethod::GetToken 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759402"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="47ffd-102">ISymUnmanagedMethod::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="47ffd-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="47ffd-103">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="47ffd-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="47ffd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47ffd-105">参数</span><span class="sxs-lookup"><span data-stu-id="47ffd-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="47ffd-106">[out]一个指向`mdMethodDef`用于接收大小，以字符为单位，包含的元数据所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="47ffd-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47ffd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="47ffd-107">Return Value</span></span>  
 <span data-ttu-id="47ffd-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="47ffd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ffd-109">要求</span><span class="sxs-lookup"><span data-stu-id="47ffd-109">Requirements</span></span>  
 <span data-ttu-id="47ffd-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47ffd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ffd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="47ffd-111">See also</span></span>

- [<span data-ttu-id="47ffd-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="47ffd-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
