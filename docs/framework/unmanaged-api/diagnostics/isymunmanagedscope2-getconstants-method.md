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
ms.openlocfilehash: f7cd45a90a750c357706f720453ff23697875b58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446233"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="7d8f2-102">ISymUnmanagedScope2::GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="7d8f2-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="7d8f2-103">获取在此范围内定义的局部变量。</span><span class="sxs-lookup"><span data-stu-id="7d8f2-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d8f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d8f2-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="7d8f2-106">中`pcConstants` 参数指向的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="7d8f2-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="7d8f2-107">弄指向 `ULONG32` 的指针，该指针接收包含常量所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="7d8f2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="7d8f2-108">弄用于存储常量的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7d8f2-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d8f2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7d8f2-109">Return Value</span></span>  
 <span data-ttu-id="7d8f2-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="7d8f2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8f2-111">要求</span><span class="sxs-lookup"><span data-stu-id="7d8f2-111">Requirements</span></span>  
 <span data-ttu-id="7d8f2-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="7d8f2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8f2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d8f2-113">See also</span></span>

- [<span data-ttu-id="7d8f2-114">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="7d8f2-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
