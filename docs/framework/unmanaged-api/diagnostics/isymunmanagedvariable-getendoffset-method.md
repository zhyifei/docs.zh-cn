---
title: "ISymUnmanagedVariable::GetEndOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7a2dac8425cd852c6c17ee1674710f6798d3b1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="c989c-102">ISymUnmanagedVariable::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c989c-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="c989c-103">获取其父项中此变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="c989c-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="c989c-104">如果这是一个作用域内的局部变量，结束偏移量将位于内定义的范围的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c989c-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c989c-105">语法</span><span class="sxs-lookup"><span data-stu-id="c989c-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c989c-106">参数</span><span class="sxs-lookup"><span data-stu-id="c989c-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c989c-107">[out]指向的指针`ULONG32`接收的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="c989c-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c989c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c989c-108">Return Value</span></span>  
 <span data-ttu-id="c989c-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c989c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c989c-110">要求</span><span class="sxs-lookup"><span data-stu-id="c989c-110">Requirements</span></span>  
 <span data-ttu-id="c989c-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c989c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c989c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c989c-112">See Also</span></span>  
 [<span data-ttu-id="c989c-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="c989c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="c989c-114">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c989c-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
