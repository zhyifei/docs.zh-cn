---
title: StackOverflowInfo 结构
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 941093b9a0856c2b716ba359c854473f3c9ea26a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006514"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="a57ec-102">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="a57ec-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="a57ec-103">存储发生的溢出的类型以及因溢出而引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="a57ec-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a57ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="a57ec-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="a57ec-105">成员</span><span class="sxs-lookup"><span data-stu-id="a57ec-105">Members</span></span>  
  
|<span data-ttu-id="a57ec-106">成员</span><span class="sxs-lookup"><span data-stu-id="a57ec-106">Member</span></span>|<span data-ttu-id="a57ec-107">描述</span><span class="sxs-lookup"><span data-stu-id="a57ec-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="a57ec-108">指定溢出类型的[StackOverflowType](stackoverflowtype-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="a57ec-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="a57ec-109">一个指向 Win32 对象的指针 `EXCEPTION_POINTERS` ，该对象包含一个异常记录，其中包含与计算机无关的异常说明和一个上下文记录，其中包含发生异常时的处理器上下文的依赖于计算机的说明。</span><span class="sxs-lookup"><span data-stu-id="a57ec-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a57ec-110">备注</span><span class="sxs-lookup"><span data-stu-id="a57ec-110">Remarks</span></span>  
 <span data-ttu-id="a57ec-111">`StackOverflowInfo`对象将传递到事件的[IActionOnCLREvent：： OnEvent](iactiononclrevent-onevent-method.md)方法 `Event_StackOverflow` 。</span><span class="sxs-lookup"><span data-stu-id="a57ec-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a57ec-112">要求</span><span class="sxs-lookup"><span data-stu-id="a57ec-112">Requirements</span></span>  
 <span data-ttu-id="a57ec-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a57ec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a57ec-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a57ec-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a57ec-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a57ec-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a57ec-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a57ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57ec-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a57ec-117">See also</span></span>

- [<span data-ttu-id="a57ec-118">承载结构</span><span class="sxs-lookup"><span data-stu-id="a57ec-118">Hosting Structures</span></span>](hosting-structures.md)
