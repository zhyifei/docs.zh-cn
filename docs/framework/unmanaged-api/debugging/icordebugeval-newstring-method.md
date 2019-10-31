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
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137646"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="7de95-102">ICorDebugEval::NewString 方法</span><span class="sxs-lookup"><span data-stu-id="7de95-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="7de95-103">分配具有指定内容的新字符串实例。</span><span class="sxs-lookup"><span data-stu-id="7de95-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de95-104">语法</span><span class="sxs-lookup"><span data-stu-id="7de95-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7de95-105">参数</span><span class="sxs-lookup"><span data-stu-id="7de95-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="7de95-106">中指向字符串内容的指针。</span><span class="sxs-lookup"><span data-stu-id="7de95-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7de95-107">备注</span><span class="sxs-lookup"><span data-stu-id="7de95-107">Remarks</span></span>  
 <span data-ttu-id="7de95-108">始终在当前执行线程的应用程序域中创建字符串。</span><span class="sxs-lookup"><span data-stu-id="7de95-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7de95-109">要求</span><span class="sxs-lookup"><span data-stu-id="7de95-109">Requirements</span></span>  
 <span data-ttu-id="7de95-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7de95-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7de95-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7de95-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7de95-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7de95-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7de95-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7de95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
