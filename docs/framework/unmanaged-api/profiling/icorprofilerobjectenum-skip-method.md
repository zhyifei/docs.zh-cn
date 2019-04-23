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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bcc837fede7e7db59bdf88a0b5434a7c1924335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210940"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="a35f8-102">ICorProfilerObjectEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="a35f8-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="a35f8-103">因此跳过指定的数量的元素，请从其当前位置前移此枚举器的光标。</span><span class="sxs-lookup"><span data-stu-id="a35f8-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a35f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="a35f8-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a35f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="a35f8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a35f8-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="a35f8-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a35f8-107">备注</span><span class="sxs-lookup"><span data-stu-id="a35f8-107">Remarks</span></span>  
 <span data-ttu-id="a35f8-108">此枚举器的光标的新位置是: （当前位置） + `celt` 。</span><span class="sxs-lookup"><span data-stu-id="a35f8-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a35f8-109">要求</span><span class="sxs-lookup"><span data-stu-id="a35f8-109">Requirements</span></span>  
 <span data-ttu-id="a35f8-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a35f8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a35f8-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a35f8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a35f8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a35f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a35f8-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a35f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35f8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a35f8-114">See also</span></span>

- [<span data-ttu-id="a35f8-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a35f8-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
