---
title: IXCLRDataModule 接口
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c8d6e36687fd43bbc59304eee64dd42eb78101e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676518"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="a6960-102">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="a6960-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="a6960-103">提供用于查询有关加载的模块的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="a6960-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="a6960-104">方法</span><span class="sxs-lookup"><span data-stu-id="a6960-104">Methods</span></span>

| <span data-ttu-id="a6960-105">方法</span><span class="sxs-lookup"><span data-stu-id="a6960-105">Method</span></span>                                                                                                                                | <span data-ttu-id="a6960-106">描述</span><span class="sxs-lookup"><span data-stu-id="a6960-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="a6960-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="a6960-107">GetMethodDefinitionByToken</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="a6960-108">获取与给定的元数据标记相对应的方法定义。</span><span class="sxs-lookup"><span data-stu-id="a6960-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="a6960-109">请求</span><span class="sxs-lookup"><span data-stu-id="a6960-109">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="a6960-110">若要填充缓冲区中提供了模块的数据的请求。</span><span class="sxs-lookup"><span data-stu-id="a6960-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="a6960-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="a6960-111">GetVersionId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="a6960-112">获取模块的版本 id。</span><span class="sxs-lookup"><span data-stu-id="a6960-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="a6960-113">备注</span><span class="sxs-lookup"><span data-stu-id="a6960-113">Remarks</span></span>

<span data-ttu-id="a6960-114">此接口存在于运行时内并不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="a6960-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a6960-115">但是，它是一个 COM 接口派生`IUnknown`具有 GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` ，可以通过常用的 COM 机制获取。</span><span class="sxs-lookup"><span data-stu-id="a6960-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6960-116">要求</span><span class="sxs-lookup"><span data-stu-id="a6960-116">Requirements</span></span>

<span data-ttu-id="a6960-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6960-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a6960-118">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="a6960-118">**Header:** None</span></span>  
<span data-ttu-id="a6960-119">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="a6960-119">**Library:** None</span></span>  
<span data-ttu-id="a6960-120">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6960-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a6960-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6960-121">See also</span></span>

- [<span data-ttu-id="a6960-122">调试</span><span class="sxs-lookup"><span data-stu-id="a6960-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a6960-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="a6960-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
