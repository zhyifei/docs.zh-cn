---
title: "ISymUnmanagedScope::GetLocalCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocalCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de8f0ee3e2a1cc13a9bdb0f59aaecd4592ea7fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="4e07f-102">ISymUnmanagedScope::GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="4e07f-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="4e07f-103">获取此范围内定义的本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="4e07f-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e07f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e07f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e07f-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e07f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4e07f-106">[out]指向的指针`ULONG32`接收本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="4e07f-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e07f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4e07f-107">Return Value</span></span>  
 <span data-ttu-id="4e07f-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="4e07f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e07f-109">要求</span><span class="sxs-lookup"><span data-stu-id="4e07f-109">Requirements</span></span>  
 <span data-ttu-id="4e07f-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e07f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e07f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e07f-111">See Also</span></span>  
 [<span data-ttu-id="4e07f-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="4e07f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
