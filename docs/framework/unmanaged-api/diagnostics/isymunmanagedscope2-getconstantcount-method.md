---
title: ISymUnmanagedScope2::GetConstantCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: f795147bdcd822db90106c7f2171eb1771b1126f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446253"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="e8b46-102">ISymUnmanagedScope2::GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="e8b46-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="e8b46-103">获取在此范围中定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="e8b46-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b46-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8b46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8b46-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8b46-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e8b46-106">弄指向 `ULONG32` 的指针，该指针接收包含常量所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="e8b46-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8b46-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e8b46-107">Return Value</span></span>  
 <span data-ttu-id="e8b46-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e8b46-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b46-109">要求</span><span class="sxs-lookup"><span data-stu-id="e8b46-109">Requirements</span></span>  
 <span data-ttu-id="e8b46-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e8b46-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b46-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8b46-111">See also</span></span>

- [<span data-ttu-id="e8b46-112">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="e8b46-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
