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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793742"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="dcd57-102">ICLRDataTarget::GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="dcd57-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="dcd57-103">获取目标进程正在使用的指令集类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="dcd57-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd57-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcd57-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcd57-105">参数</span><span class="sxs-lookup"><span data-stu-id="dcd57-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="dcd57-106">弄一个指向值的指针，该指针指示目标进程使用的指令集。</span><span class="sxs-lookup"><span data-stu-id="dcd57-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="dcd57-107">返回的 `machineType` 是在 WinNT 头文件中定义的 IMAGE_FILE_MACHINE 常量之一。</span><span class="sxs-lookup"><span data-stu-id="dcd57-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd57-108">需求</span><span class="sxs-lookup"><span data-stu-id="dcd57-108">Requirements</span></span>  
 <span data-ttu-id="dcd57-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dcd57-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd57-110">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="dcd57-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dcd57-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcd57-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcd57-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd57-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd57-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcd57-113">See also</span></span>

- [<span data-ttu-id="dcd57-114">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="dcd57-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
