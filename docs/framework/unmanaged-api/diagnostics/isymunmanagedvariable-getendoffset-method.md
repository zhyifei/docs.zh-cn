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
ms.openlocfilehash: e0f11614c6fa15034ef5fa3d68e41a936a9ff764
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427852"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="c1eb1-102">ISymUnmanagedVariable::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c1eb1-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="c1eb1-103">获取其父项中此变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="c1eb1-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="c1eb1-104">如果这是一个作用域内的局部变量，结束偏移量将位于内定义的范围的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c1eb1-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1eb1-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1eb1-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1eb1-106">参数</span><span class="sxs-lookup"><span data-stu-id="c1eb1-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c1eb1-107">[out]指向的指针`ULONG32`接收的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="c1eb1-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1eb1-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c1eb1-108">Return Value</span></span>  
 <span data-ttu-id="c1eb1-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c1eb1-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1eb1-110">要求</span><span class="sxs-lookup"><span data-stu-id="c1eb1-110">Requirements</span></span>  
 <span data-ttu-id="c1eb1-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c1eb1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1eb1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1eb1-112">See Also</span></span>  
 [<span data-ttu-id="c1eb1-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="c1eb1-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="c1eb1-114">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c1eb1-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
