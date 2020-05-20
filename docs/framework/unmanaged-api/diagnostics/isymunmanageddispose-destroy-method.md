---
title: ISymUnmanagedDispose::Destroy 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441313"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="c0a0d-102">ISymUnmanagedDispose::Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="c0a0d-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="c0a0d-103">使基础对象释放所有内部引用，并在所有后续方法调用中返回失败。</span><span class="sxs-lookup"><span data-stu-id="c0a0d-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a0d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0a0d-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c0a0d-105">返回值</span><span class="sxs-lookup"><span data-stu-id="c0a0d-105">Return Value</span></span>  
 <span data-ttu-id="c0a0d-106">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="c0a0d-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0a0d-107">要求</span><span class="sxs-lookup"><span data-stu-id="c0a0d-107">Requirements</span></span>  
 <span data-ttu-id="c0a0d-108">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c0a0d-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a0d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a0d-109">See also</span></span>

- [<span data-ttu-id="c0a0d-110">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="c0a0d-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
