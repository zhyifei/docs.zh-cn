---
title: ISymUnmanagedMethod::GetNamespace 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614482"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="fa052-102">ISymUnmanagedMethod::GetNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="fa052-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="fa052-103">获取在其中定义此方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fa052-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa052-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa052-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa052-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa052-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="fa052-106">弄设置为返回的[ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="fa052-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa052-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fa052-107">Return Value</span></span>  
 <span data-ttu-id="fa052-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fa052-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa052-109">要求</span><span class="sxs-lookup"><span data-stu-id="fa052-109">Requirements</span></span>  
 <span data-ttu-id="fa052-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fa052-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa052-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa052-111">See also</span></span>

- [<span data-ttu-id="fa052-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="fa052-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
