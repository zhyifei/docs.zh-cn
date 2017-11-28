---
title: "ISymUnmanagedScope2::GetConstants 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2.GetConstants
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4287e34828662840d1bac0d565c0d642e21de6c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="6dcda-102">ISymUnmanagedScope2::GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="6dcda-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="6dcda-103">获取此范围内定义的局部常量。</span><span class="sxs-lookup"><span data-stu-id="6dcda-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dcda-104">语法</span><span class="sxs-lookup"><span data-stu-id="6dcda-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dcda-105">参数</span><span class="sxs-lookup"><span data-stu-id="6dcda-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="6dcda-106">[in]缓冲区的长度，`pcConstants`参数指向。</span><span class="sxs-lookup"><span data-stu-id="6dcda-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="6dcda-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含常量所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6dcda-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="6dcda-108">[out]用于存储常量缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6dcda-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dcda-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6dcda-109">Return Value</span></span>  
 <span data-ttu-id="6dcda-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6dcda-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dcda-111">要求</span><span class="sxs-lookup"><span data-stu-id="6dcda-111">Requirements</span></span>  
 <span data-ttu-id="6dcda-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6dcda-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dcda-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dcda-113">See Also</span></span>  
 [<span data-ttu-id="6dcda-114">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="6dcda-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
