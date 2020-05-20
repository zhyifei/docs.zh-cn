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
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610361"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="85a7e-102">ISymUnmanagedVariable::GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="85a7e-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="85a7e-103">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="85a7e-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="85a7e-104">如果这是一个作用域内的本地变量，则起始偏移量将在为该作用域定义的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="85a7e-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a7e-105">语法</span><span class="sxs-lookup"><span data-stu-id="85a7e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85a7e-106">参数</span><span class="sxs-lookup"><span data-stu-id="85a7e-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="85a7e-107">弄指向的指针 `ULONG32` ，该指针接收开始偏移量。</span><span class="sxs-lookup"><span data-stu-id="85a7e-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85a7e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="85a7e-108">Return Value</span></span>  
 <span data-ttu-id="85a7e-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="85a7e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a7e-110">要求</span><span class="sxs-lookup"><span data-stu-id="85a7e-110">Requirements</span></span>  
 <span data-ttu-id="85a7e-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="85a7e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a7e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85a7e-112">See also</span></span>

- [<span data-ttu-id="85a7e-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="85a7e-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="85a7e-114">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="85a7e-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
