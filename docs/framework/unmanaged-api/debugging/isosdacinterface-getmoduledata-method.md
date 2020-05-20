---
title: ISOSDacInterface：： GetModuleData 方法
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
ms.openlocfilehash: b302100eb6cbfa83896cd358762c496ea01f7509
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420976"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="b58e1-102">ISOSDacInterface：： GetModuleData 方法</span><span class="sxs-lookup"><span data-stu-id="b58e1-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="b58e1-103">提取与在给定地址加载的模块对应的数据。</span><span class="sxs-lookup"><span data-stu-id="b58e1-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b58e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="b58e1-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="b58e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="b58e1-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="b58e1-106">中要为其检索信息的模块的地址。</span><span class="sxs-lookup"><span data-stu-id="b58e1-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="b58e1-107">弄用于保存已加载模块的信息的[DacpModuleData 结构](dacpmoduledata-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="b58e1-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="b58e1-108">备注</span><span class="sxs-lookup"><span data-stu-id="b58e1-108">Remarks</span></span>

<span data-ttu-id="b58e1-109">提供的方法是接口的一部分 `ISOSDacInterface` ，并且对应于虚拟方法表的第14个槽。</span><span class="sxs-lookup"><span data-stu-id="b58e1-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b58e1-110">要求</span><span class="sxs-lookup"><span data-stu-id="b58e1-110">Requirements</span></span>

<span data-ttu-id="b58e1-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b58e1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b58e1-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="b58e1-112">**Header:** None</span></span>  
<span data-ttu-id="b58e1-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="b58e1-113">**Library:** None</span></span>  
<span data-ttu-id="b58e1-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b58e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b58e1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b58e1-115">See also</span></span>

- [<span data-ttu-id="b58e1-116">调试</span><span class="sxs-lookup"><span data-stu-id="b58e1-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="b58e1-117">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="b58e1-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
