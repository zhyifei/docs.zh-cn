---
title: IXCLRDataMethodInstance 接口
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 03be79e6300afa6d25a005b0a21b8c2bf15d27be
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202270"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="ffaf7-102">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="ffaf7-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="ffaf7-103">提供用于查询方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ffaf7-104">方法</span><span class="sxs-lookup"><span data-stu-id="ffaf7-104">Methods</span></span>

| <span data-ttu-id="ffaf7-105">方法</span><span class="sxs-lookup"><span data-stu-id="ffaf7-105">Method</span></span>                                                                                                                  | <span data-ttu-id="ffaf7-106">描述</span><span class="sxs-lookup"><span data-stu-id="ffaf7-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="ffaf7-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="ffaf7-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="ffaf7-108">获取到地址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="ffaf7-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="ffaf7-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="ffaf7-110">获取方法的所有可能的入口点在本机编译的最具代表性的入口点地址。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |


## <a name="remarks"></a><span data-ttu-id="ffaf7-111">备注</span><span class="sxs-lookup"><span data-stu-id="ffaf7-111">Remarks</span></span>

<span data-ttu-id="ffaf7-112">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ffaf7-113">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ffaf7-114">要求</span><span class="sxs-lookup"><span data-stu-id="ffaf7-114">Requirements</span></span>

<span data-ttu-id="ffaf7-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffaf7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ffaf7-116">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="ffaf7-116">**Header:** None</span></span>  
<span data-ttu-id="ffaf7-117">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="ffaf7-117">**Library:** None</span></span>  
<span data-ttu-id="ffaf7-118">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ffaf7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ffaf7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffaf7-119">See also</span></span>

- [<span data-ttu-id="ffaf7-120">调试</span><span class="sxs-lookup"><span data-stu-id="ffaf7-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ffaf7-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="ffaf7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
