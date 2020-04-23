---
title: DacpGetModule 地址：请求方法
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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102902"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="f8afa-102">DacpGetModule 地址：请求方法</span><span class="sxs-lookup"><span data-stu-id="f8afa-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="f8afa-103">执行请求，从给定的运行时结构填充结构。</span><span class="sxs-lookup"><span data-stu-id="f8afa-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f8afa-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8afa-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="f8afa-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8afa-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="f8afa-106">[在]指向种子数据模块的指针。</span><span class="sxs-lookup"><span data-stu-id="f8afa-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8afa-107">备注</span><span class="sxs-lookup"><span data-stu-id="f8afa-107">Remarks</span></span>

<span data-ttu-id="f8afa-108">此结构位于运行时内，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="f8afa-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f8afa-109">要使用它，最简单的方法是模拟实现：</span><span class="sxs-lookup"><span data-stu-id="f8afa-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="f8afa-110">使用以下参数返回从调用`Request``IXCLRDataModule*`参数上的方法获得的值：`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="f8afa-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="f8afa-111">要求</span><span class="sxs-lookup"><span data-stu-id="f8afa-111">Requirements</span></span>

<span data-ttu-id="f8afa-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f8afa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="f8afa-113">**标题：** 无。</span><span class="sxs-lookup"><span data-stu-id="f8afa-113">**Header:** None\</span></span>
<span data-ttu-id="f8afa-114">**库：** 无。</span><span class="sxs-lookup"><span data-stu-id="f8afa-114">**Library:** None\</span></span>
<span data-ttu-id="f8afa-115">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8afa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f8afa-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8afa-116">See also</span></span>

- [<span data-ttu-id="f8afa-117">调试</span><span class="sxs-lookup"><span data-stu-id="f8afa-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="f8afa-118">DacpGetModule 地址结构</span><span class="sxs-lookup"><span data-stu-id="f8afa-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
