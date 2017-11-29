---
title: "ISymUnmanagedReader::GetMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 94c40555ee62bac99cf7cb34378c5b0fcca5104f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="2d783-102">ISymUnmanagedReader::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="2d783-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="2d783-103">获取符号读取器方法，给定一个方法标记。</span><span class="sxs-lookup"><span data-stu-id="2d783-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d783-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d783-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d783-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d783-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="2d783-106">[in]方法标记中。</span><span class="sxs-lookup"><span data-stu-id="2d783-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2d783-107">[out]指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2d783-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d783-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2d783-108">Return Value</span></span>  
 <span data-ttu-id="2d783-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="2d783-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d783-110">要求</span><span class="sxs-lookup"><span data-stu-id="2d783-110">Requirements</span></span>  
 <span data-ttu-id="2d783-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d783-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d783-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d783-112">See Also</span></span>  
 [<span data-ttu-id="2d783-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="2d783-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
