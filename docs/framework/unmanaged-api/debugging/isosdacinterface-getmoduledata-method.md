---
title: ISOSDacInterface::GetModuleData 方法
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 97b297def9fba329ff6d9573f7b2e7cc811273f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764724"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="94fd9-102">ISOSDacInterface::GetModuleData 方法</span><span class="sxs-lookup"><span data-stu-id="94fd9-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="94fd9-103">获取对应于在给定地址加载该模块的数据。</span><span class="sxs-lookup"><span data-stu-id="94fd9-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="94fd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="94fd9-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="94fd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="94fd9-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="94fd9-106">[in]要检索其信息的模块的地址。</span><span class="sxs-lookup"><span data-stu-id="94fd9-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="94fd9-107">[out][DacpModuleData 结构](dacpmoduledata-structure.md)来保存已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="94fd9-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="94fd9-108">备注</span><span class="sxs-lookup"><span data-stu-id="94fd9-108">Remarks</span></span>

<span data-ttu-id="94fd9-109">提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表 13 槽。</span><span class="sxs-lookup"><span data-stu-id="94fd9-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="94fd9-110">要求</span><span class="sxs-lookup"><span data-stu-id="94fd9-110">Requirements</span></span>

<span data-ttu-id="94fd9-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94fd9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="94fd9-112">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="94fd9-112">**Header:** None</span></span>  
<span data-ttu-id="94fd9-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="94fd9-113">**Library:** None</span></span>  
<span data-ttu-id="94fd9-114">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94fd9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="94fd9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="94fd9-115">See also</span></span>

- [<span data-ttu-id="94fd9-116">调试</span><span class="sxs-lookup"><span data-stu-id="94fd9-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="94fd9-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="94fd9-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
