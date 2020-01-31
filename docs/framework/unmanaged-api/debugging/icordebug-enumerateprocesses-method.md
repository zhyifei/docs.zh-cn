---
title: ICorDebug::EnumerateProcesses 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: c2a176764332eed6affda704c8bfaf546ef70880
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788992"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="b5e8e-102">ICorDebug::EnumerateProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="b5e8e-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="b5e8e-103">获取正在调试的进程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b5e8e-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5e8e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5e8e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5e8e-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="b5e8e-106">指向 ICorDebugProcessEnum 对象地址的指针，该对象是正在调试的进程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b5e8e-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e8e-107">需求</span><span class="sxs-lookup"><span data-stu-id="b5e8e-107">Requirements</span></span>  
 <span data-ttu-id="b5e8e-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5e8e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e8e-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5e8e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e8e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e8e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e8e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e8e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5e8e-112">See also</span></span>

- [<span data-ttu-id="b5e8e-113">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="b5e8e-113">ICorDebug Interface</span></span>](icordebug-interface.md)
