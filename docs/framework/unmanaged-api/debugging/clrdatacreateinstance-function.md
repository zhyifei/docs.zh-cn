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
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179364"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="765a1-102">CLRDataCreateInstance 函数</span><span class="sxs-lookup"><span data-stu-id="765a1-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="765a1-103">为指定的目标项创建接口对象。</span><span class="sxs-lookup"><span data-stu-id="765a1-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="765a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="765a1-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="765a1-105">parameters</span><span class="sxs-lookup"><span data-stu-id="765a1-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="765a1-106">[在]要实例化的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="765a1-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="765a1-107">[在]指向用户实现的[ICLRDataTarget](iclrdatatarget-interface.md)对象的指针，该对象表示要为其创建接口对象的目标项。</span><span class="sxs-lookup"><span data-stu-id="765a1-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="765a1-108">[出]指向返回接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="765a1-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="765a1-109">备注</span><span class="sxs-lookup"><span data-stu-id="765a1-109">Remarks</span></span>  
 <span data-ttu-id="765a1-110">该`ICLRDataTarget`对象由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="765a1-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="765a1-111">实现取决于表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="765a1-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="765a1-112">目标项可以是进程、内存转储、远程计算机等。</span><span class="sxs-lookup"><span data-stu-id="765a1-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="765a1-113">要求</span><span class="sxs-lookup"><span data-stu-id="765a1-113">Requirements</span></span>  
 <span data-ttu-id="765a1-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="765a1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="765a1-115">**标题：** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="765a1-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="765a1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="765a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="765a1-117">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="765a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765a1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="765a1-118">See also</span></span>

- [<span data-ttu-id="765a1-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="765a1-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
