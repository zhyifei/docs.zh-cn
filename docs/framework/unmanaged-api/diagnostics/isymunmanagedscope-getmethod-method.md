---
title: ISymUnmanagedScope::GetMethod 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: cdbffe71540b51ff539a45861546efd761761892
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615366"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="92981-102">ISymUnmanagedScope::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="92981-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="92981-103">获取包含此范围的方法。</span><span class="sxs-lookup"><span data-stu-id="92981-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92981-104">语法</span><span class="sxs-lookup"><span data-stu-id="92981-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92981-105">参数</span><span class="sxs-lookup"><span data-stu-id="92981-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="92981-106">弄指向返回的[ISymUnmanagedMethod](isymunmanagedmethod-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="92981-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92981-107">返回值</span><span class="sxs-lookup"><span data-stu-id="92981-107">Return Value</span></span>  
 <span data-ttu-id="92981-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="92981-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92981-109">要求</span><span class="sxs-lookup"><span data-stu-id="92981-109">Requirements</span></span>  
 <span data-ttu-id="92981-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="92981-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92981-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92981-111">See also</span></span>

- [<span data-ttu-id="92981-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="92981-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
