---
title: "_EFN_GetManagedObjectFieldInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectFieldInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectFieldInfo
helpviewer_keywords: _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3df09c9107b683381f21891a1001140c493a024
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="cb6b0-102">_EFN_GetManagedObjectFieldInfo 函数</span><span class="sxs-lookup"><span data-stu-id="cb6b0-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="cb6b0-103">使用提供的对象指针和字段名，获取从对象的开头到字段和字段值的偏移量。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb6b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb6b0-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb6b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb6b0-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="cb6b0-106">[in]指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="cb6b0-107">[in]托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="cb6b0-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="cb6b0-108">szFieldName</span></span>  
 <span data-ttu-id="cb6b0-109">[in]指向字段名称的托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cb6b0-110">[out]字段值。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-110">[out] The field value.</span></span> <span data-ttu-id="cb6b0-111">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="cb6b0-112">[out]从的偏移量`objAddr`到字段。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="cb6b0-113">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb6b0-114">备注</span><span class="sxs-lookup"><span data-stu-id="cb6b0-114">Remarks</span></span>  
 <span data-ttu-id="cb6b0-115">如果偏移量为 0，则写入没有偏移量。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="cb6b0-116">如果没有任何托管的代码的线程上当前上下文中，该函数将返回的错误代码为 0x1000 0xa0 设施值与 HRESULT SOS_E_NOMANAGEDCODE。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb6b0-117">要求</span><span class="sxs-lookup"><span data-stu-id="cb6b0-117">Requirements</span></span>  
 <span data-ttu-id="cb6b0-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb6b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb6b0-119">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="cb6b0-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="cb6b0-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb6b0-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6b0-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb6b0-121">See Also</span></span>  
 [<span data-ttu-id="cb6b0-122">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="cb6b0-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
