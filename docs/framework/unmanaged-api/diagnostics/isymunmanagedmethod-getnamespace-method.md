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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53a47cf67edb36b06c92be83cb23c2e1dd1e75cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424425"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="c3377-102">ISymUnmanagedMethod::GetNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="c3377-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="c3377-103">获取在其中定义此方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c3377-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3377-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3377-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3377-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3377-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c3377-106">[out]一个指针，它设置为返回[ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c3377-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3377-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c3377-107">Return Value</span></span>  
 <span data-ttu-id="c3377-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c3377-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3377-109">要求</span><span class="sxs-lookup"><span data-stu-id="c3377-109">Requirements</span></span>  
 <span data-ttu-id="c3377-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3377-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3377-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3377-111">See Also</span></span>  
 [<span data-ttu-id="c3377-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="c3377-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
