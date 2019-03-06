---
title: IXCLRDataModule::GetMethodDefinitionByToken 方法
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
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359310"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="0fa34-102">IXCLRDataModule::GetMethodDefinitionByToken 方法</span><span class="sxs-lookup"><span data-stu-id="0fa34-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="0fa34-103">获取与给定的元数据标记相对应的方法定义。</span><span class="sxs-lookup"><span data-stu-id="0fa34-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0fa34-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fa34-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="0fa34-105">参数</span><span class="sxs-lookup"><span data-stu-id="0fa34-105">Parameters</span></span>

`token`\
<span data-ttu-id="0fa34-106">[in]方法标记中。</span><span class="sxs-lookup"><span data-stu-id="0fa34-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="0fa34-107">[out]方法定义中。</span><span class="sxs-lookup"><span data-stu-id="0fa34-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fa34-108">备注</span><span class="sxs-lookup"><span data-stu-id="0fa34-108">Remarks</span></span>

<span data-ttu-id="0fa34-109">提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表 25 槽。</span><span class="sxs-lookup"><span data-stu-id="0fa34-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0fa34-110">要求</span><span class="sxs-lookup"><span data-stu-id="0fa34-110">Requirements</span></span>

<span data-ttu-id="0fa34-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fa34-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0fa34-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="0fa34-112">**Header:** None</span></span>  
<span data-ttu-id="0fa34-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="0fa34-113">**Library:** None</span></span>  
<span data-ttu-id="0fa34-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="0fa34-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa34-115">See also</span></span>

- [<span data-ttu-id="0fa34-116">调试</span><span class="sxs-lookup"><span data-stu-id="0fa34-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="0fa34-117">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="0fa34-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
