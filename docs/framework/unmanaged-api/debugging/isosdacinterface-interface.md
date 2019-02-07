---
title: ISOSDacInterface 接口
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827924"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="dd387-102">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="dd387-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="dd387-103">访问的数据提供帮助器方法`SOS`。</span><span class="sxs-lookup"><span data-stu-id="dd387-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="dd387-104">方法</span><span class="sxs-lookup"><span data-stu-id="dd387-104">Methods</span></span>

| <span data-ttu-id="dd387-105">方法</span><span class="sxs-lookup"><span data-stu-id="dd387-105">Method</span></span>                                                                                                               | <span data-ttu-id="dd387-106">描述</span><span class="sxs-lookup"><span data-stu-id="dd387-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="dd387-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="dd387-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="dd387-108">获取给定 MethodDesc 指针的数据。</span><span class="sxs-lookup"><span data-stu-id="dd387-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="dd387-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="dd387-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="dd387-110">检索对应的方法，其中包含给定的本机指令地址 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="dd387-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="dd387-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="dd387-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="dd387-112">获取对应于在给定地址加载该模块的数据。</span><span class="sxs-lookup"><span data-stu-id="dd387-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="dd387-113">备注</span><span class="sxs-lookup"><span data-stu-id="dd387-113">Remarks</span></span>

<span data-ttu-id="dd387-114">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="dd387-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="dd387-115">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="dd387-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd387-116">要求</span><span class="sxs-lookup"><span data-stu-id="dd387-116">Requirements</span></span>

<span data-ttu-id="dd387-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd387-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dd387-118">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="dd387-118">**Header:** None</span></span>  
<span data-ttu-id="dd387-119">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="dd387-119">**Library:** None</span></span>  
<span data-ttu-id="dd387-120">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dd387-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dd387-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd387-121">See also</span></span>

- [<span data-ttu-id="dd387-122">调试</span><span class="sxs-lookup"><span data-stu-id="dd387-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="dd387-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="dd387-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
