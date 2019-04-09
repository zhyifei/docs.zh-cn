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
ms.openlocfilehash: 2138dd32cf39db7b7c8989ba5827178d1a1e46c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117230"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="fff41-102">CorMethodImpl 枚举</span><span class="sxs-lookup"><span data-stu-id="fff41-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="fff41-103">包含一些值，用于描述方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="fff41-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff41-104">语法</span><span class="sxs-lookup"><span data-stu-id="fff41-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="fff41-105">成员</span><span class="sxs-lookup"><span data-stu-id="fff41-105">Members</span></span>  
  
|<span data-ttu-id="fff41-106">成员</span><span class="sxs-lookup"><span data-stu-id="fff41-106">Member</span></span>|<span data-ttu-id="fff41-107">描述</span><span class="sxs-lookup"><span data-stu-id="fff41-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="fff41-108">描述代码类型的标志。</span><span class="sxs-lookup"><span data-stu-id="fff41-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="fff41-109">指定方法实现为 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="fff41-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="fff41-110">指定方法实现为本机。</span><span class="sxs-lookup"><span data-stu-id="fff41-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="fff41-111">指定该方法的实现是 OPTIL。</span><span class="sxs-lookup"><span data-stu-id="fff41-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="fff41-112">指定该方法的实现由公共语言运行时提供。</span><span class="sxs-lookup"><span data-stu-id="fff41-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="fff41-113">指示是否是托管或非托管代码的标志。</span><span class="sxs-lookup"><span data-stu-id="fff41-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="fff41-114">指定该方法的实现不受管理。</span><span class="sxs-lookup"><span data-stu-id="fff41-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="fff41-115">指定管理方法实现。</span><span class="sxs-lookup"><span data-stu-id="fff41-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="fff41-116">指定该方法定义。</span><span class="sxs-lookup"><span data-stu-id="fff41-116">Specifies that the method is defined.</span></span> <span data-ttu-id="fff41-117">主要在合并方案中使用此标志。</span><span class="sxs-lookup"><span data-stu-id="fff41-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="fff41-118">指定方法签名不能将出错的 HRESULT 转换。</span><span class="sxs-lookup"><span data-stu-id="fff41-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="fff41-119">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="fff41-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="fff41-120">指定的方法是单线程通过其主体。</span><span class="sxs-lookup"><span data-stu-id="fff41-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="fff41-121">指定方法不能内联。</span><span class="sxs-lookup"><span data-stu-id="fff41-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="fff41-122">指定的方法应是内联在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="fff41-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="fff41-123">指定该方法不应进行优化。</span><span class="sxs-lookup"><span data-stu-id="fff41-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="fff41-124">有效的最大值`CorMethodImpl`。</span><span class="sxs-lookup"><span data-stu-id="fff41-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fff41-125">要求</span><span class="sxs-lookup"><span data-stu-id="fff41-125">Requirements</span></span>  
 <span data-ttu-id="fff41-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fff41-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fff41-127">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fff41-127">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="fff41-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fff41-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fff41-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="fff41-129">See also</span></span>

- [<span data-ttu-id="fff41-130">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="fff41-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
