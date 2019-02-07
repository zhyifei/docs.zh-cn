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
ms.openlocfilehash: 7185802a3857fcd73c63d097090a2a7809f65279
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825922"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="65a46-102">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="65a46-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="65a46-103">提供用于查询方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="65a46-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="65a46-104">方法</span><span class="sxs-lookup"><span data-stu-id="65a46-104">Methods</span></span>

| <span data-ttu-id="65a46-105">方法</span><span class="sxs-lookup"><span data-stu-id="65a46-105">Method</span></span>                                                                                                                  | <span data-ttu-id="65a46-106">描述</span><span class="sxs-lookup"><span data-stu-id="65a46-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="65a46-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="65a46-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="65a46-108">获取到地址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="65a46-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="65a46-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="65a46-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="65a46-110">获取用于本机编译的方法的所有可能的入口点的最具代表性的入口点地址...</span><span class="sxs-lookup"><span data-stu-id="65a46-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method..</span></span> |


## <a name="remarks"></a><span data-ttu-id="65a46-111">备注</span><span class="sxs-lookup"><span data-stu-id="65a46-111">Remarks</span></span>

<span data-ttu-id="65a46-112">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="65a46-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="65a46-113">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="65a46-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="65a46-114">要求</span><span class="sxs-lookup"><span data-stu-id="65a46-114">Requirements</span></span>

<span data-ttu-id="65a46-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65a46-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="65a46-116">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="65a46-116">**Header:** None</span></span>  
<span data-ttu-id="65a46-117">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="65a46-117">**Library:** None</span></span>  
<span data-ttu-id="65a46-118">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65a46-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="65a46-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="65a46-119">See also</span></span>

- [<span data-ttu-id="65a46-120">调试</span><span class="sxs-lookup"><span data-stu-id="65a46-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="65a46-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="65a46-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
