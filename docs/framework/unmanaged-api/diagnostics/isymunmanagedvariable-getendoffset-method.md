---
title: ISymUnmanagedVariable::GetEndOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 325db05cc322d85e836ca9ba62b6a169e8965241
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220950"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="e0df5-102">ISymUnmanagedVariable::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e0df5-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="e0df5-103">获取此变量在其父级内的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="e0df5-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="e0df5-104">如果这是一个作用域内的局部变量，结束偏移量将范围内为范围定义的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e0df5-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0df5-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0df5-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0df5-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0df5-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e0df5-107">[out]一个指向`ULONG32`，它接收的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="e0df5-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0df5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e0df5-108">Return Value</span></span>  
 <span data-ttu-id="e0df5-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e0df5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0df5-110">要求</span><span class="sxs-lookup"><span data-stu-id="e0df5-110">Requirements</span></span>  
 <span data-ttu-id="e0df5-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0df5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0df5-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0df5-112">See also</span></span>

- [<span data-ttu-id="e0df5-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="e0df5-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="e0df5-114">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e0df5-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
