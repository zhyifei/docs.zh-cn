---
title: "CLRDataCreateInstance 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type: COM
f1_keywords: CLRDataCreateInstance
helpviewer_keywords: CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c611cc51417199aae7c595e4edd2e9a5360f0f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="2573c-102">CLRDataCreateInstance 函数</span><span class="sxs-lookup"><span data-stu-id="2573c-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="2573c-103">创建指定的目标项的接口对象。</span><span class="sxs-lookup"><span data-stu-id="2573c-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2573c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2573c-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2573c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2573c-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="2573c-106">[in]要进行实例化的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="2573c-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="2573c-107">[in]指向用户实现[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)表示要为其创建接口对象的目标项的对象。</span><span class="sxs-lookup"><span data-stu-id="2573c-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="2573c-108">[out]指向返回的接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="2573c-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2573c-109">备注</span><span class="sxs-lookup"><span data-stu-id="2573c-109">Remarks</span></span>  
 <span data-ttu-id="2573c-110">`ICLRDataTarget`对象由调试应用程序编写器实现。</span><span class="sxs-lookup"><span data-stu-id="2573c-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="2573c-111">实现取决于所表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="2573c-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="2573c-112">目标项可能进程、 内存转储，远程计算机和等等。</span><span class="sxs-lookup"><span data-stu-id="2573c-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2573c-113">要求</span><span class="sxs-lookup"><span data-stu-id="2573c-113">Requirements</span></span>  
 <span data-ttu-id="2573c-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2573c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2573c-115">**标头：** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="2573c-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="2573c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2573c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2573c-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2573c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2573c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2573c-118">See Also</span></span>  
 [<span data-ttu-id="2573c-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="2573c-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
