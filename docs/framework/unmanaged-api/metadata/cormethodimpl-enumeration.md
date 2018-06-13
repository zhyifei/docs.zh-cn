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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4bb91423b2eaeda7d945cf14553609fd33ce9b0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443484"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="621c2-102">CorMethodImpl 枚举</span><span class="sxs-lookup"><span data-stu-id="621c2-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="621c2-103">包含一些值，用于描述方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="621c2-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="621c2-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="621c2-105">成员</span><span class="sxs-lookup"><span data-stu-id="621c2-105">Members</span></span>  
  
|<span data-ttu-id="621c2-106">成员</span><span class="sxs-lookup"><span data-stu-id="621c2-106">Member</span></span>|<span data-ttu-id="621c2-107">描述</span><span class="sxs-lookup"><span data-stu-id="621c2-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="621c2-108">描述代码类型的标志。</span><span class="sxs-lookup"><span data-stu-id="621c2-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="621c2-109">指定方法的实现是 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="621c2-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="621c2-110">指定方法实现为本机。</span><span class="sxs-lookup"><span data-stu-id="621c2-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="621c2-111">指定方法的实现是 OPTIL。</span><span class="sxs-lookup"><span data-stu-id="621c2-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="621c2-112">指定方法的实现由公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="621c2-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="621c2-113">指示是否是托管或非托管代码的标志。</span><span class="sxs-lookup"><span data-stu-id="621c2-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="621c2-114">指定方法的实现不受管理。</span><span class="sxs-lookup"><span data-stu-id="621c2-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="621c2-115">指定管理方法的实现。</span><span class="sxs-lookup"><span data-stu-id="621c2-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="621c2-116">指定定义方法。</span><span class="sxs-lookup"><span data-stu-id="621c2-116">Specifies that the method is defined.</span></span> <span data-ttu-id="621c2-117">此标志是主要用于合并方案。</span><span class="sxs-lookup"><span data-stu-id="621c2-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="621c2-118">指定方法签名，不能改变为使 HRESULT 转换。</span><span class="sxs-lookup"><span data-stu-id="621c2-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="621c2-119">保留供内部使用公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="621c2-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="621c2-120">指定的方法是单线程方式通过其正文。</span><span class="sxs-lookup"><span data-stu-id="621c2-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="621c2-121">指定方法不能内联。</span><span class="sxs-lookup"><span data-stu-id="621c2-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="621c2-122">指定该方法应内联如有可能。</span><span class="sxs-lookup"><span data-stu-id="621c2-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="621c2-123">指定该方法不应优化。</span><span class="sxs-lookup"><span data-stu-id="621c2-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="621c2-124">最大有效值`CorMethodImpl`。</span><span class="sxs-lookup"><span data-stu-id="621c2-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="621c2-125">要求</span><span class="sxs-lookup"><span data-stu-id="621c2-125">Requirements</span></span>  
 <span data-ttu-id="621c2-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="621c2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621c2-127">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="621c2-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="621c2-128">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621c2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621c2-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="621c2-129">See Also</span></span>  
 [<span data-ttu-id="621c2-130">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="621c2-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
