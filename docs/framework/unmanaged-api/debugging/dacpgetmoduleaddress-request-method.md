---
title: DacpGetModuleAddress::Request 方法
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
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860838"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="5eac8-102">DacpGetModuleAddress::Request 方法</span><span class="sxs-lookup"><span data-stu-id="5eac8-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="5eac8-103">执行从给定的运行时结构填充结构的请求。</span><span class="sxs-lookup"><span data-stu-id="5eac8-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5eac8-104">语法</span><span class="sxs-lookup"><span data-stu-id="5eac8-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="5eac8-105">参数</span><span class="sxs-lookup"><span data-stu-id="5eac8-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="5eac8-106">中指向种子数据模块的指针。</span><span class="sxs-lookup"><span data-stu-id="5eac8-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="5eac8-107">备注</span><span class="sxs-lookup"><span data-stu-id="5eac8-107">Remarks</span></span>

<span data-ttu-id="5eac8-108">此结构存在于运行时中，并且不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="5eac8-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5eac8-109">若要使用它，最简单的方法是模拟实现：</span><span class="sxs-lookup"><span data-stu-id="5eac8-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="5eac8-110">返回通过在`Request` `IXCLRDataModule*`参数上调用方法获取的值，该方法具有以下参数：`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="5eac8-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="5eac8-111">要求</span><span class="sxs-lookup"><span data-stu-id="5eac8-111">Requirements</span></span>

<span data-ttu-id="5eac8-112">**平台：** 查看[系统要求](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5eac8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="5eac8-113">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="5eac8-113">**Header:** None\</span></span>
<span data-ttu-id="5eac8-114">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="5eac8-114">**Library:** None\</span></span>
<span data-ttu-id="5eac8-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5eac8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5eac8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5eac8-116">See also</span></span>

- [<span data-ttu-id="5eac8-117">调试</span><span class="sxs-lookup"><span data-stu-id="5eac8-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="5eac8-118">DacpGetModuleAddress 结构</span><span class="sxs-lookup"><span data-stu-id="5eac8-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
