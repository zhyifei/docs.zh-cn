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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23228c1414f5f6327cfb326c95a3224ae231a033
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776781"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="ca220-102">ISymUnmanagedDispose::Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="ca220-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="ca220-103">导致要释放内部的所有引用和任何后续方法调用上返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="ca220-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca220-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca220-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ca220-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ca220-105">Return Value</span></span>  
 <span data-ttu-id="ca220-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="ca220-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca220-107">要求</span><span class="sxs-lookup"><span data-stu-id="ca220-107">Requirements</span></span>  
 <span data-ttu-id="ca220-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca220-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca220-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca220-109">See also</span></span>

- [<span data-ttu-id="ca220-110">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="ca220-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
