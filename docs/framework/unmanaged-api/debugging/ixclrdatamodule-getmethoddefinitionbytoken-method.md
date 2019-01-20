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
ms.openlocfilehash: 27f1ee28aff95340d4b533473b2f699a9405c3a2
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416377"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="b4434-102">IXCLRDataModule::GetMethodDefinitionByToken 方法</span><span class="sxs-lookup"><span data-stu-id="b4434-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="b4434-103">获取与给定的元数据标记相对应的方法定义。</span><span class="sxs-lookup"><span data-stu-id="b4434-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b4434-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4434-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

### <a name="parameters"></a><span data-ttu-id="b4434-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4434-105">Parameters</span></span>

<span data-ttu-id="b4434-106">`token` [in]方法标记中。</span><span class="sxs-lookup"><span data-stu-id="b4434-106">`token` [in] The method token.</span></span>

<span data-ttu-id="b4434-107">`methodDefinition` [out]方法定义中。</span><span class="sxs-lookup"><span data-stu-id="b4434-107">`methodDefinition` [out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4434-108">备注</span><span class="sxs-lookup"><span data-stu-id="b4434-108">Remarks</span></span>

<span data-ttu-id="b4434-109">提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表 25 槽。</span><span class="sxs-lookup"><span data-stu-id="b4434-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4434-110">要求</span><span class="sxs-lookup"><span data-stu-id="b4434-110">Requirements</span></span>

<span data-ttu-id="b4434-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4434-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b4434-112">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="b4434-112">**Header:** None</span></span>  
<span data-ttu-id="b4434-113">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="b4434-113">**Library:** None</span></span>  
<span data-ttu-id="b4434-114">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4434-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="b4434-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4434-115">See Also</span></span>

- [<span data-ttu-id="b4434-116">调试</span><span class="sxs-lookup"><span data-stu-id="b4434-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b4434-117">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="b4434-117">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
