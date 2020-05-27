---
title: CorThreadSafetyOptions 枚举
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007502"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="ef559-102">CorThreadSafetyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="ef559-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="ef559-103">指定用于选择线程安全性选项的标志。</span><span class="sxs-lookup"><span data-stu-id="ef559-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef559-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef559-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="ef559-105">成员</span><span class="sxs-lookup"><span data-stu-id="ef559-105">Members</span></span>

|<span data-ttu-id="ef559-106">成员</span><span class="sxs-lookup"><span data-stu-id="ef559-106">Member</span></span>|<span data-ttu-id="ef559-107">描述</span><span class="sxs-lookup"><span data-stu-id="ef559-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="ef559-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="ef559-108">Default value.</span></span> <span data-ttu-id="ef559-109">与 `MDThreadSafetyOff` 相同。</span><span class="sxs-lookup"><span data-stu-id="ef559-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="ef559-110">指示无法设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="ef559-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="ef559-111">指示可以设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="ef559-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="ef559-112">要求</span><span class="sxs-lookup"><span data-stu-id="ef559-112">Requirements</span></span>

<span data-ttu-id="ef559-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef559-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ef559-114">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="ef559-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="ef559-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef559-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ef559-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef559-116">See also</span></span>

- [<span data-ttu-id="ef559-117">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="ef559-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
