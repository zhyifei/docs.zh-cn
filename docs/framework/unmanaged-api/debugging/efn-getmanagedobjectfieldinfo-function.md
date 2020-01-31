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
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793762"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="90801-102">\_EFN\_GetManagedObjectFieldInfo 函数</span><span class="sxs-lookup"><span data-stu-id="90801-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="90801-103">使用提供的对象指针和字段名，获取从对象的开头到字段和字段值的偏移量。</span><span class="sxs-lookup"><span data-stu-id="90801-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90801-104">语法</span><span class="sxs-lookup"><span data-stu-id="90801-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90801-105">参数</span><span class="sxs-lookup"><span data-stu-id="90801-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="90801-106">中指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="90801-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="90801-107">中托管对象指针。</span><span class="sxs-lookup"><span data-stu-id="90801-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="90801-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="90801-108">szFieldName</span></span>  
 <span data-ttu-id="90801-109">中指向字段名称的托管对象指针。</span><span class="sxs-lookup"><span data-stu-id="90801-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="90801-110">弄字段值。</span><span class="sxs-lookup"><span data-stu-id="90801-110">[out] The field value.</span></span> <span data-ttu-id="90801-111">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="90801-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="90801-112">弄从 `objAddr` 到字段的偏移量。</span><span class="sxs-lookup"><span data-stu-id="90801-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="90801-113">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="90801-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90801-114">备注</span><span class="sxs-lookup"><span data-stu-id="90801-114">Remarks</span></span>  
 <span data-ttu-id="90801-115">如果偏移量为0，则不写入偏移量。</span><span class="sxs-lookup"><span data-stu-id="90801-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="90801-116">如果当前上下文中的线程上没有托管代码，则该函数将返回具有0xa0 的工具值的 HRESULT SOS_E_NOMANAGEDCODE 和错误代码0x1000。</span><span class="sxs-lookup"><span data-stu-id="90801-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90801-117">需求</span><span class="sxs-lookup"><span data-stu-id="90801-117">Requirements</span></span>  
 <span data-ttu-id="90801-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90801-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90801-119">**标头：** SOS_Stacktrace。h</span><span class="sxs-lookup"><span data-stu-id="90801-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="90801-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90801-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90801-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90801-121">See also</span></span>

- [<span data-ttu-id="90801-122">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="90801-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
