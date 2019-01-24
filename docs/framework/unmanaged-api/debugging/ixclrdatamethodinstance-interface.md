---
title: IXCLRDataMethodInstance 接口
ms.date: 01/16/2019
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
ms.openlocfilehash: 0eef69cea9f59911b5076f56579b0192be357431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659106"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="b321c-102">IXCLRDataMethodInstance 接口</span><span class="sxs-lookup"><span data-stu-id="b321c-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="b321c-103">提供用于查询方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="b321c-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="b321c-104">方法</span><span class="sxs-lookup"><span data-stu-id="b321c-104">Methods</span></span>

| <span data-ttu-id="b321c-105">方法</span><span class="sxs-lookup"><span data-stu-id="b321c-105">Method</span></span>                                                                                                                  | <span data-ttu-id="b321c-106">描述</span><span class="sxs-lookup"><span data-stu-id="b321c-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="b321c-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="b321c-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="b321c-108">获取到地址映射信息的 IL。</span><span class="sxs-lookup"><span data-stu-id="b321c-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b321c-109">备注</span><span class="sxs-lookup"><span data-stu-id="b321c-109">Remarks</span></span>

<span data-ttu-id="b321c-110">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="b321c-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b321c-111">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="b321c-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="b321c-112">要求</span><span class="sxs-lookup"><span data-stu-id="b321c-112">Requirements</span></span>

<span data-ttu-id="b321c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b321c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b321c-114">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="b321c-114">**Header:** None</span></span>  
<span data-ttu-id="b321c-115">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="b321c-115">**Library:** None</span></span>  
<span data-ttu-id="b321c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b321c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b321c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b321c-117">See also</span></span>

- [<span data-ttu-id="b321c-118">调试</span><span class="sxs-lookup"><span data-stu-id="b321c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b321c-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="b321c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
