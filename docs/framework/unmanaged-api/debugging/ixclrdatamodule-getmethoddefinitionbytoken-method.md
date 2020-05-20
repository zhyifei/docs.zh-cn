---
title: IXCLRDataModule：： GetMethodDefinitionByToken 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 074949145be588fc34266a9f2ee501caeeffb9d3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420872"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="28eb6-102">IXCLRDataModule：： GetMethodDefinitionByToken 方法</span><span class="sxs-lookup"><span data-stu-id="28eb6-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="28eb6-103">获取对应于给定元数据标记的方法定义。</span><span class="sxs-lookup"><span data-stu-id="28eb6-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="28eb6-104">语法</span><span class="sxs-lookup"><span data-stu-id="28eb6-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="28eb6-105">参数</span><span class="sxs-lookup"><span data-stu-id="28eb6-105">Parameters</span></span>

`token`\
<span data-ttu-id="28eb6-106">中方法标记。</span><span class="sxs-lookup"><span data-stu-id="28eb6-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="28eb6-107">弄方法定义。</span><span class="sxs-lookup"><span data-stu-id="28eb6-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="28eb6-108">备注</span><span class="sxs-lookup"><span data-stu-id="28eb6-108">Remarks</span></span>

<span data-ttu-id="28eb6-109">提供的方法是接口的一部分 `IXCLRDataModule` ，并且对应于虚拟方法表的26个槽。</span><span class="sxs-lookup"><span data-stu-id="28eb6-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="28eb6-110">要求</span><span class="sxs-lookup"><span data-stu-id="28eb6-110">Requirements</span></span>

<span data-ttu-id="28eb6-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28eb6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="28eb6-112">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="28eb6-112">**Header:** None</span></span>  
<span data-ttu-id="28eb6-113">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="28eb6-113">**Library:** None</span></span>  
<span data-ttu-id="28eb6-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="28eb6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="28eb6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28eb6-115">See also</span></span>

- [<span data-ttu-id="28eb6-116">调试</span><span class="sxs-lookup"><span data-stu-id="28eb6-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="28eb6-117">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="28eb6-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
