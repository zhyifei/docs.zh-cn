---
title: ISymUnmanagedMethod::GetRootScope 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: 650a64e72b410cddfbee7dce676ddbb5a3b8b3d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614443"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="2f1c7-102">ISymUnmanagedMethod::GetRootScope 方法</span><span class="sxs-lookup"><span data-stu-id="2f1c7-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="2f1c7-103">获取此方法内的根词法范围。</span><span class="sxs-lookup"><span data-stu-id="2f1c7-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="2f1c7-104">此范围包括整个方法。</span><span class="sxs-lookup"><span data-stu-id="2f1c7-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f1c7-105">语法</span><span class="sxs-lookup"><span data-stu-id="2f1c7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f1c7-106">参数</span><span class="sxs-lookup"><span data-stu-id="2f1c7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2f1c7-107">弄设置为返回的[ISymUnmanagedScope](isymunmanagedscope-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2f1c7-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f1c7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2f1c7-108">Return Value</span></span>  
 <span data-ttu-id="2f1c7-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2f1c7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f1c7-110">要求</span><span class="sxs-lookup"><span data-stu-id="2f1c7-110">Requirements</span></span>  
 <span data-ttu-id="2f1c7-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2f1c7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1c7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f1c7-112">See also</span></span>

- [<span data-ttu-id="2f1c7-113">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="2f1c7-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
