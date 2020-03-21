---
title: ISymUnmanagedScope2::GetConstants 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176612"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="e82f9-102">ISymUnmanagedScope2::GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="e82f9-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="e82f9-103">获取在此作用域中定义的本地常量。</span><span class="sxs-lookup"><span data-stu-id="e82f9-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="e82f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e82f9-105">parameters</span><span class="sxs-lookup"><span data-stu-id="e82f9-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="e82f9-106">[在]`pcConstants`参数指向的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="e82f9-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="e82f9-107">[出]指向 的指针`ULONG32`，该指针以字符形式接收包含常量所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="e82f9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="e82f9-108">[出]存储常量的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e82f9-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e82f9-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e82f9-109">Return Value</span></span>  
 <span data-ttu-id="e82f9-110">如果方法成功，S_OK;否则，E_FAIL或其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e82f9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e82f9-111">要求</span><span class="sxs-lookup"><span data-stu-id="e82f9-111">Requirements</span></span>  
 <span data-ttu-id="e82f9-112">**标题：** 科西姆.伊德尔，科西姆.h</span><span class="sxs-lookup"><span data-stu-id="e82f9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82f9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e82f9-113">See also</span></span>

- [<span data-ttu-id="e82f9-114">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="e82f9-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
