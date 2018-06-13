---
title: ICorDebugProcess2::GetVersion 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1f850e85099a466c497a8fcc822bce9510f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416375"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="02c87-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="02c87-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="02c87-103">获取在此进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="02c87-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c87-104">语法</span><span class="sxs-lookup"><span data-stu-id="02c87-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02c87-105">参数</span><span class="sxs-lookup"><span data-stu-id="02c87-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="02c87-106">[out]指向存储运行时的版本号 COR_VERSION 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="02c87-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02c87-107">备注</span><span class="sxs-lookup"><span data-stu-id="02c87-107">Remarks</span></span>  
 <span data-ttu-id="02c87-108">`GetVersion`方法返回错误代码，如果已在进程中不加载任何运行时。</span><span class="sxs-lookup"><span data-stu-id="02c87-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02c87-109">要求</span><span class="sxs-lookup"><span data-stu-id="02c87-109">Requirements</span></span>  
 <span data-ttu-id="02c87-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02c87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c87-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02c87-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02c87-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02c87-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02c87-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c87-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
