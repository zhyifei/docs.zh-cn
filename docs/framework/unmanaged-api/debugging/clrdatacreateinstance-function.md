---
title: CLRDataCreateInstance 函数
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a839eb2edd36dc726c819a819fd4d427fbaea40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740988"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="4cc41-102">CLRDataCreateInstance 函数</span><span class="sxs-lookup"><span data-stu-id="4cc41-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="4cc41-103">创建指定的目标项的接口对象。</span><span class="sxs-lookup"><span data-stu-id="4cc41-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc41-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cc41-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc41-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cc41-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="4cc41-106">[in]若要实例化的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="4cc41-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="4cc41-107">[in]指向用户实现的指针[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)对象，表示要为其创建的接口对象的目标项。</span><span class="sxs-lookup"><span data-stu-id="4cc41-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="4cc41-108">[out]指向返回的接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4cc41-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cc41-109">备注</span><span class="sxs-lookup"><span data-stu-id="4cc41-109">Remarks</span></span>  
 <span data-ttu-id="4cc41-110">`ICLRDataTarget`对象由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="4cc41-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="4cc41-111">实现取决于所表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="4cc41-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="4cc41-112">目标项可能是进程、 内存转储、 远程计算机，等等。</span><span class="sxs-lookup"><span data-stu-id="4cc41-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc41-113">要求</span><span class="sxs-lookup"><span data-stu-id="4cc41-113">Requirements</span></span>  
 <span data-ttu-id="4cc41-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc41-115">**标头：** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="4cc41-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="4cc41-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc41-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc41-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cc41-118">See also</span></span>

- [<span data-ttu-id="4cc41-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4cc41-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
