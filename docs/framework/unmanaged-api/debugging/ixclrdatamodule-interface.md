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
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790396"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="8275c-102">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="8275c-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="8275c-103">提供用于查询有关已加载模块的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="8275c-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8275c-104">方法</span><span class="sxs-lookup"><span data-stu-id="8275c-104">Methods</span></span>

| <span data-ttu-id="8275c-105">方法</span><span class="sxs-lookup"><span data-stu-id="8275c-105">Method</span></span>                                                                                                                                | <span data-ttu-id="8275c-106">描述</span><span class="sxs-lookup"><span data-stu-id="8275c-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="8275c-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="8275c-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="8275c-108">获取对应于给定元数据标记的方法定义。</span><span class="sxs-lookup"><span data-stu-id="8275c-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="8275c-109">请求</span><span class="sxs-lookup"><span data-stu-id="8275c-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="8275c-110">请求填充模块数据所提供的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8275c-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="8275c-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="8275c-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="8275c-112">获取模块的版本 ID。</span><span class="sxs-lookup"><span data-stu-id="8275c-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="8275c-113">备注</span><span class="sxs-lookup"><span data-stu-id="8275c-113">Remarks</span></span>

<span data-ttu-id="8275c-114">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="8275c-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8275c-115">不过，它是一个使用 GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。</span><span class="sxs-lookup"><span data-stu-id="8275c-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8275c-116">需求</span><span class="sxs-lookup"><span data-stu-id="8275c-116">Requirements</span></span>

<span data-ttu-id="8275c-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8275c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8275c-118">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="8275c-118">**Header:** None</span></span>  
<span data-ttu-id="8275c-119">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="8275c-119">**Library:** None</span></span>  
<span data-ttu-id="8275c-120">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8275c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8275c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8275c-121">See also</span></span>

- [<span data-ttu-id="8275c-122">调试</span><span class="sxs-lookup"><span data-stu-id="8275c-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="8275c-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="8275c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
