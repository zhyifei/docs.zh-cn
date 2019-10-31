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
ms.openlocfilehash: 941d1b4057ef78a6235a0ba853e48a000f2087e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122888"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="8fd9a-102">ICLRDataTarget::GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="8fd9a-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="8fd9a-103">获取目标进程正在使用的指令集类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="8fd9a-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd9a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8fd9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fd9a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8fd9a-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="8fd9a-106">弄一个指向值的指针，该指针指示目标进程使用的指令集。</span><span class="sxs-lookup"><span data-stu-id="8fd9a-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="8fd9a-107">返回的 `machineType` 是在 WinNT 头文件中定义的 IMAGE_FILE_MACHINE 常量之一。</span><span class="sxs-lookup"><span data-stu-id="8fd9a-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd9a-108">要求</span><span class="sxs-lookup"><span data-stu-id="8fd9a-108">Requirements</span></span>  
 <span data-ttu-id="8fd9a-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd9a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd9a-110">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="8fd9a-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8fd9a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd9a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd9a-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd9a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fd9a-113">See also</span></span>

- [<span data-ttu-id="8fd9a-114">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="8fd9a-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
