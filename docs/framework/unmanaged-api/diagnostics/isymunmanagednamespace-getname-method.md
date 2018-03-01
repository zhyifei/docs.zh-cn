---
title: "ISymUnmanagedNamespace::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b29e71a9a1185a7080f71b1621a07dd7ae41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="1043a-102">ISymUnmanagedNamespace::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="1043a-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="1043a-103">获取此命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="1043a-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1043a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1043a-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1043a-105">参数</span><span class="sxs-lookup"><span data-stu-id="1043a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1043a-106">[in]A `ULONG32` ，该值指示的大小`szName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1043a-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1043a-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含命名空间名称，包括 null 终止所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1043a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="1043a-108">[out]指向包含命名空间名称的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="1043a-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1043a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1043a-109">Return Value</span></span>  
 <span data-ttu-id="1043a-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="1043a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1043a-111">惠?</span><span class="sxs-lookup"><span data-stu-id="1043a-111">Requirements</span></span>  
 <span data-ttu-id="1043a-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1043a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1043a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1043a-113">See Also</span></span>  
 [<span data-ttu-id="1043a-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="1043a-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
