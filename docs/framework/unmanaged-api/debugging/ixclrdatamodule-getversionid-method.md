---
title: IXCLRDataModule::GetVersionId 方法
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
ms.openlocfilehash: 6ec18bcf079c7687df4ac9b7c5db23b84383c517
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632295"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="65330-102">IXCLRDataModule::GetVersionId 方法</span><span class="sxs-lookup"><span data-stu-id="65330-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="65330-103">获取模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="65330-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="65330-104">语法</span><span class="sxs-lookup"><span data-stu-id="65330-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="65330-105">参数</span><span class="sxs-lookup"><span data-stu-id="65330-105">Parameters</span></span>

`vid`\
<span data-ttu-id="65330-106">[out]模块的版本标识符。</span><span class="sxs-lookup"><span data-stu-id="65330-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="65330-107">备注</span><span class="sxs-lookup"><span data-stu-id="65330-107">Remarks</span></span>

<span data-ttu-id="65330-108">提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表的 40 槽。</span><span class="sxs-lookup"><span data-stu-id="65330-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="65330-109">要求</span><span class="sxs-lookup"><span data-stu-id="65330-109">Requirements</span></span>

<span data-ttu-id="65330-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65330-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="65330-111">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="65330-111">**Header:** None</span></span>  
<span data-ttu-id="65330-112">**库：** None</span><span class="sxs-lookup"><span data-stu-id="65330-112">**Library:** None</span></span>  
<span data-ttu-id="65330-113">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65330-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="65330-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="65330-114">See also</span></span>

- [<span data-ttu-id="65330-115">调试</span><span class="sxs-lookup"><span data-stu-id="65330-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="65330-116">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="65330-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
