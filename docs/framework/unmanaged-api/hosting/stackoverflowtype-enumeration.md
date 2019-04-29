---
title: StackOverflowType 枚举
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8541ea7b614ff4a6ca666f0e2549a7f50e190192
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777957"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="7397e-102">StackOverflowType 枚举</span><span class="sxs-lookup"><span data-stu-id="7397e-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="7397e-103">包含堆栈溢出事件的根本原因的值。</span><span class="sxs-lookup"><span data-stu-id="7397e-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7397e-104">语法</span><span class="sxs-lookup"><span data-stu-id="7397e-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="7397e-105">成员</span><span class="sxs-lookup"><span data-stu-id="7397e-105">Members</span></span>  
  
|<span data-ttu-id="7397e-106">成员</span><span class="sxs-lookup"><span data-stu-id="7397e-106">Member</span></span>|<span data-ttu-id="7397e-107">描述</span><span class="sxs-lookup"><span data-stu-id="7397e-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="7397e-108">由执行引擎引发堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="7397e-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="7397e-109">由托管代码导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="7397e-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="7397e-110">由非托管代码导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="7397e-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7397e-111">备注</span><span class="sxs-lookup"><span data-stu-id="7397e-111">Remarks</span></span>  
 <span data-ttu-id="7397e-112">此信息传递到主机上，通过调用[iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7397e-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7397e-113">要求</span><span class="sxs-lookup"><span data-stu-id="7397e-113">Requirements</span></span>  
 <span data-ttu-id="7397e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7397e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7397e-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7397e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7397e-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7397e-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7397e-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7397e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7397e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7397e-118">See also</span></span>

- [<span data-ttu-id="7397e-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="7397e-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
