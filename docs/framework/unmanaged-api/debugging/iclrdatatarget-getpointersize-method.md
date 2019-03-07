---
title: ICLRDataTarget::GetPointerSize 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b85739f0f9b6771b204f0e0297ab025cd112a12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476696"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="f4ddf-102">ICLRDataTarget::GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="f4ddf-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="f4ddf-103">获取用字节表示，目标进程使用的指针类型的大小。</span><span class="sxs-lookup"><span data-stu-id="f4ddf-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="f4ddf-104">由公共语言运行时数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="f4ddf-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ddf-105">语法</span><span class="sxs-lookup"><span data-stu-id="f4ddf-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4ddf-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4ddf-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="f4ddf-107">[out]指向一个整数值，指定的大小，以字节为单位，在目标进程上的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f4ddf-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4ddf-108">备注</span><span class="sxs-lookup"><span data-stu-id="f4ddf-108">Remarks</span></span>  
 <span data-ttu-id="f4ddf-109">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="f4ddf-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ddf-110">要求</span><span class="sxs-lookup"><span data-stu-id="f4ddf-110">Requirements</span></span>  
 <span data-ttu-id="f4ddf-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ddf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ddf-112">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f4ddf-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f4ddf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4ddf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4ddf-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ddf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ddf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4ddf-115">See also</span></span>
- [<span data-ttu-id="f4ddf-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="f4ddf-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
