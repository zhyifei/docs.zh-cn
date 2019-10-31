---
title: ICorPublish::EnumProcesses 方法
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121794"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="27991-102">ICorPublish::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="27991-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="27991-103">获取在此计算机上运行的托管进程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="27991-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27991-104">语法</span><span class="sxs-lookup"><span data-stu-id="27991-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27991-105">参数</span><span class="sxs-lookup"><span data-stu-id="27991-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="27991-106">[COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)枚举的一个值，该值指定要检索的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="27991-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="27991-107">在当前版本中，只有 COR_PUB_MANAGEDONLY 是有效的。</span><span class="sxs-lookup"><span data-stu-id="27991-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="27991-108">一个指针，指向作为进程枚举器的[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="27991-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27991-109">备注</span><span class="sxs-lookup"><span data-stu-id="27991-109">Remarks</span></span>  
 <span data-ttu-id="27991-110">枚举器的进程集合基于在调用 `EnumProcesses` 方法时正在运行的进程的快照。</span><span class="sxs-lookup"><span data-stu-id="27991-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="27991-111">枚举器将不包含在调用 `EnumProcesses` 之后终止或启动的任何进程。</span><span class="sxs-lookup"><span data-stu-id="27991-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="27991-112">在此[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)实例上，可以多次调用 `EnumProcesses` 方法，以创建新的最新进程集合。</span><span class="sxs-lookup"><span data-stu-id="27991-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="27991-113">`EnumProcesses` 方法的后续调用将不会影响现有集合。</span><span class="sxs-lookup"><span data-stu-id="27991-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27991-114">要求</span><span class="sxs-lookup"><span data-stu-id="27991-114">Requirements</span></span>  
 <span data-ttu-id="27991-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27991-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27991-116">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="27991-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="27991-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27991-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27991-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27991-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27991-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="27991-119">See also</span></span>

- [<span data-ttu-id="27991-120">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="27991-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
