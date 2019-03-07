---
title: PFN_CLRDataCreateInstance 函数指针
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19d7284399719dd848af43765a392802a589fc33
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492525"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="95f0a-102">PFN_CLRDataCreateInstance 函数指针</span><span class="sxs-lookup"><span data-stu-id="95f0a-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="95f0a-103">指向一个函数来创建一个接口对象，用于指定的目标项。</span><span class="sxs-lookup"><span data-stu-id="95f0a-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="95f0a-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="95f0a-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="95f0a-106">[in]若要实例化的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="95f0a-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="95f0a-107">[in]指向用户实现的指针[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)对象，表示要为其创建的接口对象的目标项。</span><span class="sxs-lookup"><span data-stu-id="95f0a-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="95f0a-108">[out]指向返回的接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="95f0a-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f0a-109">备注</span><span class="sxs-lookup"><span data-stu-id="95f0a-109">Remarks</span></span>  
 <span data-ttu-id="95f0a-110">`ICLRDataTarget`对象由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="95f0a-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="95f0a-111">实现取决于所表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="95f0a-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="95f0a-112">目标项可能是进程、 内存转储、 远程计算机，等等。</span><span class="sxs-lookup"><span data-stu-id="95f0a-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f0a-113">要求</span><span class="sxs-lookup"><span data-stu-id="95f0a-113">Requirements</span></span>  
 <span data-ttu-id="95f0a-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95f0a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f0a-115">**标头：** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="95f0a-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="95f0a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f0a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f0a-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f0a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f0a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="95f0a-118">See also</span></span>
- [<span data-ttu-id="95f0a-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="95f0a-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
