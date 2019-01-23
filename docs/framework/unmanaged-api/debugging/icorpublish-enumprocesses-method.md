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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3af824a23d683f4d450ef6f60fd407928c41d51e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536953"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="00b5b-102">ICorPublish::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="00b5b-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="00b5b-103">获取此计算机上运行的托管进程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="00b5b-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="00b5b-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00b5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="00b5b-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="00b5b-106">值为[COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)枚举，用于指定要检索的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="00b5b-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="00b5b-107">在最新版本，仅 COR_PUB_MANAGEDONLY 是有效的。</span><span class="sxs-lookup"><span data-stu-id="00b5b-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="00b5b-108">指向的地址的指针[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)是进程的枚举器的实例。</span><span class="sxs-lookup"><span data-stu-id="00b5b-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00b5b-109">备注</span><span class="sxs-lookup"><span data-stu-id="00b5b-109">Remarks</span></span>  
 <span data-ttu-id="00b5b-110">枚举器的进程集合基于时正在运行的进程的快照`EnumProcesses`调用方法。</span><span class="sxs-lookup"><span data-stu-id="00b5b-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="00b5b-111">枚举器将不包括任何进程，终止之前或之后开始`EnumProcesses`调用。</span><span class="sxs-lookup"><span data-stu-id="00b5b-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="00b5b-112">`EnumProcesses`不止一次调用方法时可能会对此[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)实例以创建新的进程的最新集合。</span><span class="sxs-lookup"><span data-stu-id="00b5b-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="00b5b-113">后续调用将不会影响现有集合`EnumProcesses`方法。</span><span class="sxs-lookup"><span data-stu-id="00b5b-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00b5b-114">要求</span><span class="sxs-lookup"><span data-stu-id="00b5b-114">Requirements</span></span>  
 <span data-ttu-id="00b5b-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00b5b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00b5b-116">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="00b5b-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="00b5b-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00b5b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00b5b-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00b5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b5b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="00b5b-119">See also</span></span>
- [<span data-ttu-id="00b5b-120">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="00b5b-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
