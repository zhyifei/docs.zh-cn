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
ms.openlocfilehash: 73645265821d5854776e412f8eb0f33b36db00d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698169"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="50a19-102">ICLRDataTarget::GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="50a19-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="50a19-103">获取用字节表示，目标进程使用的指针类型的大小。</span><span class="sxs-lookup"><span data-stu-id="50a19-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="50a19-104">由公共语言运行时数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="50a19-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a19-105">语法</span><span class="sxs-lookup"><span data-stu-id="50a19-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50a19-106">参数</span><span class="sxs-lookup"><span data-stu-id="50a19-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="50a19-107">[out]指向一个整数值，指定的大小，以字节为单位，在目标进程上的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="50a19-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50a19-108">备注</span><span class="sxs-lookup"><span data-stu-id="50a19-108">Remarks</span></span>  
 <span data-ttu-id="50a19-109">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="50a19-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a19-110">要求</span><span class="sxs-lookup"><span data-stu-id="50a19-110">Requirements</span></span>  
 <span data-ttu-id="50a19-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50a19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a19-112">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="50a19-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="50a19-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a19-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a19-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="50a19-115">See also</span></span>

- [<span data-ttu-id="50a19-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="50a19-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
