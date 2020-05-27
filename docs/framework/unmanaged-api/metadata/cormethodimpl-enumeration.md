---
title: CorMethodImpl 枚举
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: b32e8f0b03ef6d550c384f3d932cc295a7270028
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007658"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="f98eb-102">CorMethodImpl 枚举</span><span class="sxs-lookup"><span data-stu-id="f98eb-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="f98eb-103">包含一些值，用于描述方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="f98eb-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="f98eb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="f98eb-105">成员</span><span class="sxs-lookup"><span data-stu-id="f98eb-105">Members</span></span>  
  
|<span data-ttu-id="f98eb-106">成员</span><span class="sxs-lookup"><span data-stu-id="f98eb-106">Member</span></span>|<span data-ttu-id="f98eb-107">描述</span><span class="sxs-lookup"><span data-stu-id="f98eb-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="f98eb-108">描述代码类型的标志。</span><span class="sxs-lookup"><span data-stu-id="f98eb-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="f98eb-109">指定方法实现为 Microsoft 中间语言（MSIL）。</span><span class="sxs-lookup"><span data-stu-id="f98eb-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="f98eb-110">指定方法实现为本机。</span><span class="sxs-lookup"><span data-stu-id="f98eb-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="f98eb-111">指定方法实现为 OPTIL。</span><span class="sxs-lookup"><span data-stu-id="f98eb-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="f98eb-112">指定方法实现由公共语言运行时提供。</span><span class="sxs-lookup"><span data-stu-id="f98eb-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="f98eb-113">指示代码是托管代码还是非托管代码的标志。</span><span class="sxs-lookup"><span data-stu-id="f98eb-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="f98eb-114">指定方法实现是不受管理的。</span><span class="sxs-lookup"><span data-stu-id="f98eb-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="f98eb-115">指定方法实现是托管的。</span><span class="sxs-lookup"><span data-stu-id="f98eb-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="f98eb-116">指定定义方法。</span><span class="sxs-lookup"><span data-stu-id="f98eb-116">Specifies that the method is defined.</span></span> <span data-ttu-id="f98eb-117">此标志主要用于合并方案。</span><span class="sxs-lookup"><span data-stu-id="f98eb-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="f98eb-118">指定方法签名不能用于 HRESULT 转换。</span><span class="sxs-lookup"><span data-stu-id="f98eb-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="f98eb-119">保留供公共语言运行时内部使用。</span><span class="sxs-lookup"><span data-stu-id="f98eb-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="f98eb-120">指定方法是通过其主体单线程的。</span><span class="sxs-lookup"><span data-stu-id="f98eb-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="f98eb-121">指定方法不能内联。</span><span class="sxs-lookup"><span data-stu-id="f98eb-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="f98eb-122">指定方法应尽可能内联。</span><span class="sxs-lookup"><span data-stu-id="f98eb-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="f98eb-123">指定不应优化方法。</span><span class="sxs-lookup"><span data-stu-id="f98eb-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="f98eb-124">的最大有效值 `CorMethodImpl` 。</span><span class="sxs-lookup"><span data-stu-id="f98eb-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f98eb-125">要求</span><span class="sxs-lookup"><span data-stu-id="f98eb-125">Requirements</span></span>  
 <span data-ttu-id="f98eb-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f98eb-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f98eb-127">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="f98eb-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f98eb-128">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f98eb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98eb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f98eb-129">See also</span></span>

- [<span data-ttu-id="f98eb-130">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="f98eb-130">Metadata Enumerations</span></span>](metadata-enumerations.md)
