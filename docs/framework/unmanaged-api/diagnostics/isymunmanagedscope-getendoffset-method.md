---
title: "ISymUnmanagedScope::GetEndOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dd3b7c78c3a43109c3508487aa34650f0f16d196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="296bc-102">ISymUnmanagedScope::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="296bc-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="296bc-103">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="296bc-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="296bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="296bc-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="296bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="296bc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="296bc-106">[out]指向的指针`ULONG32`接收的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="296bc-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="296bc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="296bc-107">Return Value</span></span>  
 <span data-ttu-id="296bc-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="296bc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="296bc-109">要求</span><span class="sxs-lookup"><span data-stu-id="296bc-109">Requirements</span></span>  
 <span data-ttu-id="296bc-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="296bc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296bc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="296bc-111">See Also</span></span>  
 [<span data-ttu-id="296bc-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="296bc-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="296bc-113">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="296bc-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
