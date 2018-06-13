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
ms.openlocfilehash: d9d4965751db1a70871270317a644b0acb1302f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405975"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="4aa41-102">CLRDataCreateInstance 函数</span><span class="sxs-lookup"><span data-stu-id="4aa41-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="4aa41-103">创建指定的目标项的接口对象。</span><span class="sxs-lookup"><span data-stu-id="4aa41-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa41-104">语法</span><span class="sxs-lookup"><span data-stu-id="4aa41-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aa41-105">参数</span><span class="sxs-lookup"><span data-stu-id="4aa41-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="4aa41-106">[in]要进行实例化的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="4aa41-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="4aa41-107">[in]指向用户实现[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)表示要为其创建接口对象的目标项的对象。</span><span class="sxs-lookup"><span data-stu-id="4aa41-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="4aa41-108">[out]指向返回的接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4aa41-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4aa41-109">备注</span><span class="sxs-lookup"><span data-stu-id="4aa41-109">Remarks</span></span>  
 <span data-ttu-id="4aa41-110">`ICLRDataTarget`对象由调试应用程序编写器实现。</span><span class="sxs-lookup"><span data-stu-id="4aa41-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="4aa41-111">实现取决于所表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="4aa41-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="4aa41-112">目标项可能进程、 内存转储，远程计算机和等等。</span><span class="sxs-lookup"><span data-stu-id="4aa41-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aa41-113">要求</span><span class="sxs-lookup"><span data-stu-id="4aa41-113">Requirements</span></span>  
 <span data-ttu-id="4aa41-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aa41-115">**标头：** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="4aa41-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="4aa41-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4aa41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4aa41-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aa41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa41-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4aa41-118">See Also</span></span>  
 [<span data-ttu-id="4aa41-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4aa41-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
