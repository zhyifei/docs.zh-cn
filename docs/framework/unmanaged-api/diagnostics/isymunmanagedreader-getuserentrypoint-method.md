---
title: "ISymUnmanagedReader::GetUserEntryPoint 方法"
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
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 328f44e797a49a899545fa43d940a3b0399ee8c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="3cb1c-102">ISymUnmanagedReader::GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="3cb1c-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="3cb1c-103">如果有，则返回指定为该模块的用户入口点的方法。</span><span class="sxs-lookup"><span data-stu-id="3cb1c-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="3cb1c-104">例如，用户的主要方法，而不是编译器生成存根 （stub） 的主要方法之前，可能是此方法。</span><span class="sxs-lookup"><span data-stu-id="3cb1c-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb1c-105">语法</span><span class="sxs-lookup"><span data-stu-id="3cb1c-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cb1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="3cb1c-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="3cb1c-107">[out]指向接收的入口点的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="3cb1c-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cb1c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3cb1c-108">Return Value</span></span>  
 <span data-ttu-id="3cb1c-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="3cb1c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cb1c-110">惠?</span><span class="sxs-lookup"><span data-stu-id="3cb1c-110">Requirements</span></span>  
 <span data-ttu-id="3cb1c-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3cb1c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb1c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cb1c-112">See Also</span></span>  
 [<span data-ttu-id="3cb1c-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="3cb1c-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
