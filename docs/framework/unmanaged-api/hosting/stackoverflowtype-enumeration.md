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
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006450"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="a266d-102">StackOverflowType 枚举</span><span class="sxs-lookup"><span data-stu-id="a266d-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="a266d-103">包含指示堆栈溢出事件的根本原因的值。</span><span class="sxs-lookup"><span data-stu-id="a266d-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a266d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a266d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="a266d-105">成员</span><span class="sxs-lookup"><span data-stu-id="a266d-105">Members</span></span>  
  
|<span data-ttu-id="a266d-106">成员</span><span class="sxs-lookup"><span data-stu-id="a266d-106">Member</span></span>|<span data-ttu-id="a266d-107">描述</span><span class="sxs-lookup"><span data-stu-id="a266d-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="a266d-108">堆栈溢出由执行引擎引起。</span><span class="sxs-lookup"><span data-stu-id="a266d-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="a266d-109">堆栈溢出由托管代码引起。</span><span class="sxs-lookup"><span data-stu-id="a266d-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="a266d-110">堆栈溢出由非托管代码引起。</span><span class="sxs-lookup"><span data-stu-id="a266d-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a266d-111">备注</span><span class="sxs-lookup"><span data-stu-id="a266d-111">Remarks</span></span>  
 <span data-ttu-id="a266d-112">此信息通过调用[IActionOnCLREvent：： OnEvent](iactiononclrevent-onevent-method.md)方法传递到主机。</span><span class="sxs-lookup"><span data-stu-id="a266d-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a266d-113">要求</span><span class="sxs-lookup"><span data-stu-id="a266d-113">Requirements</span></span>  
 <span data-ttu-id="a266d-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a266d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a266d-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a266d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a266d-116">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a266d-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a266d-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a266d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a266d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a266d-118">See also</span></span>

- [<span data-ttu-id="a266d-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="a266d-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
