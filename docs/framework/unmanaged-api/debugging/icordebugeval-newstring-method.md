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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989022"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="31c33-102">ICorDebugEval::NewString 方法</span><span class="sxs-lookup"><span data-stu-id="31c33-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="31c33-103">分配新的字符串实例具有指定的内容。</span><span class="sxs-lookup"><span data-stu-id="31c33-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31c33-104">语法</span><span class="sxs-lookup"><span data-stu-id="31c33-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31c33-105">参数</span><span class="sxs-lookup"><span data-stu-id="31c33-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="31c33-106">[in]指向字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="31c33-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31c33-107">备注</span><span class="sxs-lookup"><span data-stu-id="31c33-107">Remarks</span></span>  
 <span data-ttu-id="31c33-108">始终在线程当前执行的应用程序域中创建的字符串。</span><span class="sxs-lookup"><span data-stu-id="31c33-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31c33-109">要求</span><span class="sxs-lookup"><span data-stu-id="31c33-109">Requirements</span></span>  
 <span data-ttu-id="31c33-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31c33-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31c33-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31c33-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31c33-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31c33-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31c33-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31c33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
