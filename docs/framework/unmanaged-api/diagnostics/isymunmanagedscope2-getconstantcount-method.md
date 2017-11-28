---
title: "ISymUnmanagedScope2::GetConstantCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstantCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 26ce28c3542af80f033cc765c3e462a34e4fb3e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="36264-102">ISymUnmanagedScope2::GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="36264-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="36264-103">获取此范围内定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="36264-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36264-104">语法</span><span class="sxs-lookup"><span data-stu-id="36264-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36264-105">参数</span><span class="sxs-lookup"><span data-stu-id="36264-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="36264-106">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含常量所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="36264-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36264-107">返回值</span><span class="sxs-lookup"><span data-stu-id="36264-107">Return Value</span></span>  
 <span data-ttu-id="36264-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="36264-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36264-109">要求</span><span class="sxs-lookup"><span data-stu-id="36264-109">Requirements</span></span>  
 <span data-ttu-id="36264-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36264-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36264-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36264-111">See Also</span></span>  
 [<span data-ttu-id="36264-112">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="36264-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
