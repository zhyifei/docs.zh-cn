---
title: ICorDebugEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 9f0fda803ba3a1ce35017d85e84b3bf6f567eda0
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976364"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="4fe67-102">ICorDebugEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="4fe67-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="4fe67-103">创建此 ICorDebugEnum 对象的副本。</span><span class="sxs-lookup"><span data-stu-id="4fe67-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe67-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fe67-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fe67-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fe67-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4fe67-106">弄指向作为此`ICorDebugEnum` `ICorDebugEnum`对象副本的对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4fe67-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fe67-107">要求</span><span class="sxs-lookup"><span data-stu-id="4fe67-107">Requirements</span></span>  
 <span data-ttu-id="4fe67-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4fe67-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe67-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fe67-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fe67-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fe67-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fe67-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe67-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
