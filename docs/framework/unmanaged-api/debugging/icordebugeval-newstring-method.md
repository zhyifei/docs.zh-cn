---
title: "ICorDebugEval::NewString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 48c1a36e32feb94e8399c46f88a98f75c81fdb6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="637ba-102">ICorDebugEval::NewString 方法</span><span class="sxs-lookup"><span data-stu-id="637ba-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="637ba-103">分配具有指定内容的新字符串实例。</span><span class="sxs-lookup"><span data-stu-id="637ba-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="637ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="637ba-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="637ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="637ba-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="637ba-106">[in]指向字符串的内容的指针。</span><span class="sxs-lookup"><span data-stu-id="637ba-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="637ba-107">备注</span><span class="sxs-lookup"><span data-stu-id="637ba-107">Remarks</span></span>  
 <span data-ttu-id="637ba-108">始终在线程当前执行的应用程序域中创建字符串。</span><span class="sxs-lookup"><span data-stu-id="637ba-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="637ba-109">要求</span><span class="sxs-lookup"><span data-stu-id="637ba-109">Requirements</span></span>  
 <span data-ttu-id="637ba-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="637ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="637ba-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="637ba-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="637ba-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="637ba-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="637ba-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="637ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
