---
title: ICorDebugEval::NewString 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: b263fed7db5cb2ef687da45f8cbc99a02e1e3ea2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976130"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="dd63d-102">ICorDebugEval::NewString 方法</span><span class="sxs-lookup"><span data-stu-id="dd63d-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="dd63d-103">分配具有指定内容的新字符串实例。</span><span class="sxs-lookup"><span data-stu-id="dd63d-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd63d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd63d-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd63d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd63d-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="dd63d-106">中指向字符串内容的指针。</span><span class="sxs-lookup"><span data-stu-id="dd63d-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd63d-107">备注</span><span class="sxs-lookup"><span data-stu-id="dd63d-107">Remarks</span></span>  
 <span data-ttu-id="dd63d-108">始终在当前执行线程的应用程序域中创建字符串。</span><span class="sxs-lookup"><span data-stu-id="dd63d-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd63d-109">要求</span><span class="sxs-lookup"><span data-stu-id="dd63d-109">Requirements</span></span>  
 <span data-ttu-id="dd63d-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd63d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd63d-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd63d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd63d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd63d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd63d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd63d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
