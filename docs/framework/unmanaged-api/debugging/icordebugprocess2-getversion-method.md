---
title: "ICorDebugProcess2::GetVersion 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetVersion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae9c80a65908d6ec1514ce64845217bd7b5c7805
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="feb3f-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="feb3f-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="feb3f-103">获取在此进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="feb3f-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb3f-104">语法</span><span class="sxs-lookup"><span data-stu-id="feb3f-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="feb3f-105">参数</span><span class="sxs-lookup"><span data-stu-id="feb3f-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="feb3f-106">[out]指向存储运行时的版本号 COR_VERSION 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="feb3f-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feb3f-107">备注</span><span class="sxs-lookup"><span data-stu-id="feb3f-107">Remarks</span></span>  
 <span data-ttu-id="feb3f-108">`GetVersion`方法返回错误代码，如果已在进程中不加载任何运行时。</span><span class="sxs-lookup"><span data-stu-id="feb3f-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb3f-109">惠?</span><span class="sxs-lookup"><span data-stu-id="feb3f-109">Requirements</span></span>  
 <span data-ttu-id="feb3f-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="feb3f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb3f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feb3f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feb3f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feb3f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feb3f-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb3f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
