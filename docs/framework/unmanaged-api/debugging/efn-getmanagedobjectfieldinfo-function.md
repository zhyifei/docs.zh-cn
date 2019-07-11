---
title: _EFN_GetManagedObjectFieldInfo 函数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1de0b3b05d38c1fec38b9436c653973dfaa4136
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739011"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="4a52a-102">\_EFN\_GetManagedObjectFieldInfo Function</span><span class="sxs-lookup"><span data-stu-id="4a52a-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="4a52a-103">使用提供的对象指针和字段名，获取从对象的开头到字段和字段值的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4a52a-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a52a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a52a-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a52a-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a52a-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="4a52a-106">[in]指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="4a52a-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="4a52a-107">[in]托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="4a52a-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="4a52a-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="4a52a-108">szFieldName</span></span>  
 <span data-ttu-id="4a52a-109">[in]指向字段名称的托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="4a52a-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4a52a-110">[out]字段值中。</span><span class="sxs-lookup"><span data-stu-id="4a52a-110">[out] The field value.</span></span> <span data-ttu-id="4a52a-111">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="4a52a-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="4a52a-112">[out]从偏移量`objAddr`的字段。</span><span class="sxs-lookup"><span data-stu-id="4a52a-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="4a52a-113">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="4a52a-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a52a-114">备注</span><span class="sxs-lookup"><span data-stu-id="4a52a-114">Remarks</span></span>  
 <span data-ttu-id="4a52a-115">如果偏移量为 0，则编写没有偏移量。</span><span class="sxs-lookup"><span data-stu-id="4a52a-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="4a52a-116">如果没有任何托管的代码的线程上当前上下文中，该函数返回 HRESULT SOS_E_NOMANAGEDCODE 0xa0 设施值和错误代码为 0x1000。</span><span class="sxs-lookup"><span data-stu-id="4a52a-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a52a-117">要求</span><span class="sxs-lookup"><span data-stu-id="4a52a-117">Requirements</span></span>  
 <span data-ttu-id="4a52a-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a52a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a52a-119">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="4a52a-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="4a52a-120">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a52a-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a52a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a52a-121">See also</span></span>

- [<span data-ttu-id="4a52a-122">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4a52a-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
