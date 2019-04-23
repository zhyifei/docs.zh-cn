---
title: DacpGetModuleAddress::Request Method
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111678"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="ab989-102">DacpGetModuleAddress::Request Method</span><span class="sxs-lookup"><span data-stu-id="ab989-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="ab989-103">执行请求以填充从给定的运行时结构的结构。</span><span class="sxs-lookup"><span data-stu-id="ab989-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ab989-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab989-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="ab989-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab989-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="ab989-106">[in]指向种子数据模块的指针。</span><span class="sxs-lookup"><span data-stu-id="ab989-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab989-107">备注</span><span class="sxs-lookup"><span data-stu-id="ab989-107">Remarks</span></span>

<span data-ttu-id="ab989-108">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="ab989-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ab989-109">若要使用它，最简单方法是模拟实现：</span><span class="sxs-lookup"><span data-stu-id="ab989-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="ab989-110">返回通过调用获取的值`Request`方法`IXCLRDataModule*`参数使用以下参数： `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="ab989-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="ab989-111">要求</span><span class="sxs-lookup"><span data-stu-id="ab989-111">Requirements</span></span>

<span data-ttu-id="ab989-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab989-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ab989-113">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="ab989-113">**Header:** None</span></span>     
<span data-ttu-id="ab989-114">**库：** None</span><span class="sxs-lookup"><span data-stu-id="ab989-114">**Library:** None</span></span>  
<span data-ttu-id="ab989-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ab989-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ab989-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab989-116">See also</span></span>

- [<span data-ttu-id="ab989-117">调试</span><span class="sxs-lookup"><span data-stu-id="ab989-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="ab989-118">DacpGetModuleAddress Interface</span><span class="sxs-lookup"><span data-stu-id="ab989-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)