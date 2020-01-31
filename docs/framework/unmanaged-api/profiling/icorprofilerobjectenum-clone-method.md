---
title: ICorProfilerObjectEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: 8153dbd27e168e3a5bd8e5aeada955a0382aaf75
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868247"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="25185-102">ICorProfilerObjectEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="25185-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="25185-103">获取一个接口指针，该指针指向此[ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)接口的副本。</span><span class="sxs-lookup"><span data-stu-id="25185-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25185-104">语法</span><span class="sxs-lookup"><span data-stu-id="25185-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25185-105">参数</span><span class="sxs-lookup"><span data-stu-id="25185-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="25185-106">弄指向接口指针的指针，该指针指向此 `ICorProfilerObjectEnum` 接口的副本。</span><span class="sxs-lookup"><span data-stu-id="25185-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="25185-107">副本单独维护自己的枚举状态。</span><span class="sxs-lookup"><span data-stu-id="25185-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="25185-108">但是，副本的初始光标位置将与此枚举器的当前游标位置相同。</span><span class="sxs-lookup"><span data-stu-id="25185-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25185-109">需求</span><span class="sxs-lookup"><span data-stu-id="25185-109">Requirements</span></span>  
 <span data-ttu-id="25185-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25185-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25185-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25185-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25185-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25185-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25185-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25185-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25185-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25185-114">See also</span></span>

- [<span data-ttu-id="25185-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="25185-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
