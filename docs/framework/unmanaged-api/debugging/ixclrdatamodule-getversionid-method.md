---
title: IXCLRDataModule：： GetVersionId 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395281"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="bc8d6-102">IXCLRDataModule：： GetVersionId 方法</span><span class="sxs-lookup"><span data-stu-id="bc8d6-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="bc8d6-103">获取模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="bc8d6-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bc8d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc8d6-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="bc8d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc8d6-105">Parameters</span></span>

`vid`\
<span data-ttu-id="bc8d6-106">弄模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="bc8d6-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc8d6-107">备注</span><span class="sxs-lookup"><span data-stu-id="bc8d6-107">Remarks</span></span>

<span data-ttu-id="bc8d6-108">提供的方法是接口的一部分 `IXCLRDataModule` ，并且对应于虚拟方法表的第41届槽。</span><span class="sxs-lookup"><span data-stu-id="bc8d6-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc8d6-109">要求</span><span class="sxs-lookup"><span data-stu-id="bc8d6-109">Requirements</span></span>

<span data-ttu-id="bc8d6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc8d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bc8d6-111">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="bc8d6-111">**Header:** None</span></span>  
<span data-ttu-id="bc8d6-112">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="bc8d6-112">**Library:** None</span></span>  
<span data-ttu-id="bc8d6-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bc8d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bc8d6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc8d6-114">See also</span></span>

- [<span data-ttu-id="bc8d6-115">调试</span><span class="sxs-lookup"><span data-stu-id="bc8d6-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="bc8d6-116">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="bc8d6-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
