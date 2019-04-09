---
title: _EFN_GetManagedObjectName 函数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a95008d98436161ac919ef307273bc797519f15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080613"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="e9476-102">_EFN_GetManagedObjectName 函数</span><span class="sxs-lookup"><span data-stu-id="e9476-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="e9476-103">获取使用提供的托管的对象指针的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="e9476-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9476-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9476-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9476-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9476-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="e9476-106">[in]指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="e9476-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="e9476-107">[in]托管的对象指针。</span><span class="sxs-lookup"><span data-stu-id="e9476-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="e9476-108">szName</span><span class="sxs-lookup"><span data-stu-id="e9476-108">szName</span></span>  
 <span data-ttu-id="e9476-109">[out]类型的名称。</span><span class="sxs-lookup"><span data-stu-id="e9476-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="e9476-110">[out]字符串缓冲区中有可用的字符数。</span><span class="sxs-lookup"><span data-stu-id="e9476-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9476-111">备注</span><span class="sxs-lookup"><span data-stu-id="e9476-111">Remarks</span></span>  
 <span data-ttu-id="e9476-112">如果没有任何托管的代码的线程上当前上下文中，该函数返回 HRESULT SOS_E_NOMANAGEDCODE 0xa0 设施值和错误代码为 0x1000。</span><span class="sxs-lookup"><span data-stu-id="e9476-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9476-113">要求</span><span class="sxs-lookup"><span data-stu-id="e9476-113">Requirements</span></span>  
 <span data-ttu-id="e9476-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9476-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9476-115">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="e9476-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="e9476-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e9476-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9476-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9476-117">See also</span></span>

- [<span data-ttu-id="e9476-118">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e9476-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
