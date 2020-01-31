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
ms.openlocfilehash: 5f785b22a3fbda6403c124ec70757b16f5335907
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790758"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="e0c6d-102">ICorPublish::EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="e0c6d-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="e0c6d-103">获取在此计算机上运行的托管进程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0c6d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c6d-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0c6d-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="e0c6d-106">一个[COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md)枚举的值，该值指定要检索的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="e0c6d-107">在当前版本中，只有 COR_PUB_MANAGEDONLY 是有效的。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="e0c6d-108">一个指针，指向作为进程枚举器的[ICorPublishProcessEnum](icorpublishprocessenum-interface.md)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c6d-109">备注</span><span class="sxs-lookup"><span data-stu-id="e0c6d-109">Remarks</span></span>  
 <span data-ttu-id="e0c6d-110">枚举器的进程集合基于在调用 `EnumProcesses` 方法时正在运行的进程的快照。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="e0c6d-111">枚举器将不包含在调用 `EnumProcesses` 之后终止或启动的任何进程。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="e0c6d-112">在此[ICorPublish](icorpublish-interface.md)实例上，可以多次调用 `EnumProcesses` 方法，以创建新的最新进程集合。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="e0c6d-113">`EnumProcesses` 方法的后续调用将不会影响现有集合。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c6d-114">需求</span><span class="sxs-lookup"><span data-stu-id="e0c6d-114">Requirements</span></span>  
 <span data-ttu-id="e0c6d-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c6d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c6d-116">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="e0c6d-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e0c6d-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0c6d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0c6d-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c6d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c6d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0c6d-119">See also</span></span>

- [<span data-ttu-id="e0c6d-120">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="e0c6d-120">ICorPublish Interface</span></span>](icorpublish-interface.md)
