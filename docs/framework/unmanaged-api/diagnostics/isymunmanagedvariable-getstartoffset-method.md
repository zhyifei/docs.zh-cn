---
title: ISymUnmanagedVariable::GetStartOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 996f9af1bccb446ad4fcc6faec60b88e511262de
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474275"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="87aac-102">ISymUnmanagedVariable::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="87aac-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="87aac-103">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="87aac-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="87aac-104">如果这是一个作用域内的本地变量，则起始偏移量将范围内为范围定义的偏移量。</span><span class="sxs-lookup"><span data-stu-id="87aac-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87aac-105">语法</span><span class="sxs-lookup"><span data-stu-id="87aac-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87aac-106">参数</span><span class="sxs-lookup"><span data-stu-id="87aac-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="87aac-107">[out]一个指向`ULONG32`，它接收的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="87aac-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87aac-108">返回值</span><span class="sxs-lookup"><span data-stu-id="87aac-108">Return Value</span></span>  
 <span data-ttu-id="87aac-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="87aac-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87aac-110">要求</span><span class="sxs-lookup"><span data-stu-id="87aac-110">Requirements</span></span>  
 <span data-ttu-id="87aac-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="87aac-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87aac-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="87aac-112">See also</span></span>
- [<span data-ttu-id="87aac-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="87aac-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="87aac-114">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="87aac-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
