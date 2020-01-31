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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790411"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="b0331-102">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="b0331-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="b0331-103">提供用于查询有关方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="b0331-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="b0331-104">方法</span><span class="sxs-lookup"><span data-stu-id="b0331-104">Methods</span></span>

| <span data-ttu-id="b0331-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0331-105">Method</span></span>                                                                                                                  | <span data-ttu-id="b0331-106">描述</span><span class="sxs-lookup"><span data-stu-id="b0331-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="b0331-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="b0331-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="b0331-108">获取用于寻址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="b0331-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="b0331-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="b0331-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="b0331-110">获取方法的所有可能入口点的本机编译的最具代表性的入口点地址。</span><span class="sxs-lookup"><span data-stu-id="b0331-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b0331-111">备注</span><span class="sxs-lookup"><span data-stu-id="b0331-111">Remarks</span></span>

<span data-ttu-id="b0331-112">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="b0331-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b0331-113">不过，它是一个使用 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。</span><span class="sxs-lookup"><span data-stu-id="b0331-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="b0331-114">需求</span><span class="sxs-lookup"><span data-stu-id="b0331-114">Requirements</span></span>

<span data-ttu-id="b0331-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0331-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b0331-116">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="b0331-116">**Header:** None</span></span>  
<span data-ttu-id="b0331-117">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="b0331-117">**Library:** None</span></span>  
<span data-ttu-id="b0331-118">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b0331-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b0331-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0331-119">See also</span></span>

- [<span data-ttu-id="b0331-120">调试</span><span class="sxs-lookup"><span data-stu-id="b0331-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="b0331-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="b0331-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
