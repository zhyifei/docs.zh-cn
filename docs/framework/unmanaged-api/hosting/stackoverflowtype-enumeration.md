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
ms.openlocfilehash: 06c9119a2b842a0efcd4af752ba72dbfda03bf13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653850"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="9ee4b-102">StackOverflowType 枚举</span><span class="sxs-lookup"><span data-stu-id="9ee4b-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="9ee4b-103">包含堆栈溢出事件的根本原因的值。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ee4b-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="9ee4b-105">成员</span><span class="sxs-lookup"><span data-stu-id="9ee4b-105">Members</span></span>  
  
|<span data-ttu-id="9ee4b-106">成员</span><span class="sxs-lookup"><span data-stu-id="9ee4b-106">Member</span></span>|<span data-ttu-id="9ee4b-107">描述</span><span class="sxs-lookup"><span data-stu-id="9ee4b-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="9ee4b-108">由执行引擎引发堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="9ee4b-109">由托管代码导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="9ee4b-110">由非托管代码导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee4b-111">备注</span><span class="sxs-lookup"><span data-stu-id="9ee4b-111">Remarks</span></span>  
 <span data-ttu-id="9ee4b-112">此信息传递到主机上，通过调用[iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee4b-113">要求</span><span class="sxs-lookup"><span data-stu-id="9ee4b-113">Requirements</span></span>  
 <span data-ttu-id="9ee4b-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ee4b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee4b-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ee4b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ee4b-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ee4b-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee4b-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee4b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee4b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ee4b-118">See also</span></span>
- [<span data-ttu-id="9ee4b-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="9ee4b-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
