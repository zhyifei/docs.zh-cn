---
title: IXCLRData模块：获取方法定义令牌方法
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
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176664"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="bd9dd-102">IXCLRData模块：获取方法定义令牌方法</span><span class="sxs-lookup"><span data-stu-id="bd9dd-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="bd9dd-103">获取与给定元数据令牌对应的方法定义。</span><span class="sxs-lookup"><span data-stu-id="bd9dd-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bd9dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd9dd-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="bd9dd-105">parameters</span><span class="sxs-lookup"><span data-stu-id="bd9dd-105">Parameters</span></span>

`token`\
<span data-ttu-id="bd9dd-106">[在]方法令牌。</span><span class="sxs-lookup"><span data-stu-id="bd9dd-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="bd9dd-107">[出]方法定义。</span><span class="sxs-lookup"><span data-stu-id="bd9dd-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd9dd-108">备注</span><span class="sxs-lookup"><span data-stu-id="bd9dd-108">Remarks</span></span>

<span data-ttu-id="bd9dd-109">提供的方法是接口的一`IXCLRDataModule`部分，对应于虚拟方法表的第 25 个插槽。</span><span class="sxs-lookup"><span data-stu-id="bd9dd-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd9dd-110">要求</span><span class="sxs-lookup"><span data-stu-id="bd9dd-110">Requirements</span></span>

<span data-ttu-id="bd9dd-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd9dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bd9dd-112">**标题：** 没有</span><span class="sxs-lookup"><span data-stu-id="bd9dd-112">**Header:** None</span></span>  
<span data-ttu-id="bd9dd-113">**库：** 没有</span><span class="sxs-lookup"><span data-stu-id="bd9dd-113">**Library:** None</span></span>  
<span data-ttu-id="bd9dd-114">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bd9dd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd9dd-115">See also</span></span>

- [<span data-ttu-id="bd9dd-116">调试</span><span class="sxs-lookup"><span data-stu-id="bd9dd-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="bd9dd-117">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="bd9dd-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
