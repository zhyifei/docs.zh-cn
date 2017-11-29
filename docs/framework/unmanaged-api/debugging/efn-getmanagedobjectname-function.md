---
title: "_EFN_GetManagedObjectName 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectName
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectName
helpviewer_keywords: _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80e36f6c60c4c305cad9176cd7f185d8b6d2fdf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="45ed9-102">_EFN_GetManagedObjectName 函数</span><span class="sxs-lookup"><span data-stu-id="45ed9-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="45ed9-103">获取使用提供的托管的对象指针的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="45ed9-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ed9-104">语法</span><span class="sxs-lookup"><span data-stu-id="45ed9-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45ed9-105">参数</span><span class="sxs-lookup"><span data-stu-id="45ed9-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="45ed9-106">[in]指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="45ed9-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="45ed9-107">[in]托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="45ed9-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="45ed9-108">szName</span><span class="sxs-lookup"><span data-stu-id="45ed9-108">szName</span></span>  
 <span data-ttu-id="45ed9-109">[out]类型的名称。</span><span class="sxs-lookup"><span data-stu-id="45ed9-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="45ed9-110">[out]字符串缓冲区中可用的字符数。</span><span class="sxs-lookup"><span data-stu-id="45ed9-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45ed9-111">备注</span><span class="sxs-lookup"><span data-stu-id="45ed9-111">Remarks</span></span>  
 <span data-ttu-id="45ed9-112">如果没有任何托管的代码的线程上当前上下文中，该函数将返回的错误代码为 0x1000 0xa0 设施值与 HRESULT SOS_E_NOMANAGEDCODE。</span><span class="sxs-lookup"><span data-stu-id="45ed9-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45ed9-113">要求</span><span class="sxs-lookup"><span data-stu-id="45ed9-113">Requirements</span></span>  
 <span data-ttu-id="45ed9-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45ed9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ed9-115">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="45ed9-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="45ed9-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ed9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ed9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45ed9-117">See Also</span></span>  
 [<span data-ttu-id="45ed9-118">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="45ed9-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
