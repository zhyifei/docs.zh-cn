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
ms.openlocfilehash: ed151f998ed7d28ba7ae170839ce2fa3a1ee6135
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490445"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="ad044-102">ISOSDacInterface::GetModuleData 方法</span><span class="sxs-lookup"><span data-stu-id="ad044-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="ad044-103">获取对应于在给定地址加载该模块的数据。</span><span class="sxs-lookup"><span data-stu-id="ad044-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ad044-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad044-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="ad044-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad044-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="ad044-106">[in]要检索其信息的模块的地址。</span><span class="sxs-lookup"><span data-stu-id="ad044-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="ad044-107">[out][DacpModuleData 结构](dacpmoduledata-structure.md)来保存已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ad044-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>


## <a name="remarks"></a><span data-ttu-id="ad044-108">备注</span><span class="sxs-lookup"><span data-stu-id="ad044-108">Remarks</span></span>

<span data-ttu-id="ad044-109">提供的方法属于`ISOSDacInterface`接口，并对应于虚拟方法表 13 槽。</span><span class="sxs-lookup"><span data-stu-id="ad044-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad044-110">要求</span><span class="sxs-lookup"><span data-stu-id="ad044-110">Requirements</span></span>

<span data-ttu-id="ad044-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad044-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ad044-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="ad044-112">**Header:** None</span></span>  
<span data-ttu-id="ad044-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="ad044-113">**Library:** None</span></span>  
<span data-ttu-id="ad044-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad044-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad044-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad044-115">See also</span></span>

- [<span data-ttu-id="ad044-116">调试</span><span class="sxs-lookup"><span data-stu-id="ad044-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="ad044-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="ad044-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)