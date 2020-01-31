---
title: ICorProfilerObjectEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 096489fcdc9d604e003386501c22967b45ba6d7f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861094"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="d0f1c-102">ICorProfilerObjectEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="d0f1c-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="d0f1c-103">将此枚举器的光标从其当前位置前移，以便跳过指定数目的元素。</span><span class="sxs-lookup"><span data-stu-id="d0f1c-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0f1c-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0f1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0f1c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d0f1c-106">中要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="d0f1c-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0f1c-107">备注</span><span class="sxs-lookup"><span data-stu-id="d0f1c-107">Remarks</span></span>  
 <span data-ttu-id="d0f1c-108">此枚举器的游标的新位置为：（当前位置） + `celt`。</span><span class="sxs-lookup"><span data-stu-id="d0f1c-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0f1c-109">需求</span><span class="sxs-lookup"><span data-stu-id="d0f1c-109">Requirements</span></span>  
 <span data-ttu-id="d0f1c-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0f1c-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0f1c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0f1c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0f1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0f1c-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0f1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f1c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0f1c-114">See also</span></span>

- [<span data-ttu-id="d0f1c-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d0f1c-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
