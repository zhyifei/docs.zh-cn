---
title: ISymUnmanagedScope::GetLocalCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611258"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="cd5fe-102">ISymUnmanagedScope::GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="cd5fe-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="cd5fe-103">获取在此范围内定义的局部变量的计数。</span><span class="sxs-lookup"><span data-stu-id="cd5fe-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd5fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd5fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd5fe-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="cd5fe-106">弄指向的指针 `ULONG32` ，该指针接收局部变量的计数。</span><span class="sxs-lookup"><span data-stu-id="cd5fe-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd5fe-107">返回值</span><span class="sxs-lookup"><span data-stu-id="cd5fe-107">Return Value</span></span>  
 <span data-ttu-id="cd5fe-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="cd5fe-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd5fe-109">要求</span><span class="sxs-lookup"><span data-stu-id="cd5fe-109">Requirements</span></span>  
 <span data-ttu-id="cd5fe-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cd5fe-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5fe-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd5fe-111">See also</span></span>

- [<span data-ttu-id="cd5fe-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="cd5fe-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
