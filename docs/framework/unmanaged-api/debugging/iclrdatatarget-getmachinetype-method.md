---
title: ICLRDataTarget::GetMachineType 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c515a8184e8c01b0e292057f3f66ffef28f2c5fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402876"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="e5a22-102">ICLRDataTarget::GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="e5a22-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="e5a22-103">获取目标进程正在使用的指令集的种类的标识符。</span><span class="sxs-lookup"><span data-stu-id="e5a22-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a22-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5a22-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5a22-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5a22-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="e5a22-106">[out]指向一个值，指示的指令集的目标进程正在使用。</span><span class="sxs-lookup"><span data-stu-id="e5a22-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="e5a22-107">返回`machineType`是在 WinNT.h 中的标头文件中定义的 IMAGE_FILE_MACHINE 常量之一。</span><span class="sxs-lookup"><span data-stu-id="e5a22-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a22-108">要求</span><span class="sxs-lookup"><span data-stu-id="e5a22-108">Requirements</span></span>  
 <span data-ttu-id="e5a22-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a22-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a22-110">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e5a22-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e5a22-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a22-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a22-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a22-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a22-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a22-113">See Also</span></span>  
 [<span data-ttu-id="e5a22-114">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e5a22-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
