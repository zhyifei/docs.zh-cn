---
title: ISymUnmanagedScope::GetLocalCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b3c9c637bdaa0d0e18dbfd9655790ff5ebd46f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141838"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="61a3d-102">ISymUnmanagedScope::GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="61a3d-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="61a3d-103">获取此范围内定义的本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="61a3d-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="61a3d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61a3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="61a3d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="61a3d-106">[out]一个指向`ULONG32`用于接收本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="61a3d-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61a3d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="61a3d-107">Return Value</span></span>  
 <span data-ttu-id="61a3d-108">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="61a3d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a3d-109">要求</span><span class="sxs-lookup"><span data-stu-id="61a3d-109">Requirements</span></span>  
 <span data-ttu-id="61a3d-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61a3d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a3d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="61a3d-111">See also</span></span>

- [<span data-ttu-id="61a3d-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="61a3d-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
