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
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739227"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="9cfcd-102">DacpGetModuleAddress::Request Method</span><span class="sxs-lookup"><span data-stu-id="9cfcd-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="9cfcd-103">执行请求以填充从给定的运行时结构的结构。</span><span class="sxs-lookup"><span data-stu-id="9cfcd-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9cfcd-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cfcd-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="9cfcd-105">参数</span><span class="sxs-lookup"><span data-stu-id="9cfcd-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="9cfcd-106">[in]指向种子数据模块的指针。</span><span class="sxs-lookup"><span data-stu-id="9cfcd-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="9cfcd-107">备注</span><span class="sxs-lookup"><span data-stu-id="9cfcd-107">Remarks</span></span>

<span data-ttu-id="9cfcd-108">此结构存在于运行时内，不通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="9cfcd-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9cfcd-109">若要使用它，最简单方法是模拟实现：</span><span class="sxs-lookup"><span data-stu-id="9cfcd-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="9cfcd-110">返回通过调用获取的值`Request`方法`IXCLRDataModule*`参数使用以下参数： `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="9cfcd-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="9cfcd-111">要求</span><span class="sxs-lookup"><span data-stu-id="9cfcd-111">Requirements</span></span>

<span data-ttu-id="9cfcd-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cfcd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9cfcd-113">**标头：** None</span><span class="sxs-lookup"><span data-stu-id="9cfcd-113">**Header:** None</span></span>     
<span data-ttu-id="9cfcd-114">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="9cfcd-114">**Library:** None</span></span>  
<span data-ttu-id="9cfcd-115">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9cfcd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9cfcd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cfcd-116">See also</span></span>

- [<span data-ttu-id="9cfcd-117">调试</span><span class="sxs-lookup"><span data-stu-id="9cfcd-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="9cfcd-118">DacpGetModuleAddress Interface</span><span class="sxs-lookup"><span data-stu-id="9cfcd-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
