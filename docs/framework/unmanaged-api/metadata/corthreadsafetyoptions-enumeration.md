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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045222"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="2782d-102">CorThreadSafetyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="2782d-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="2782d-103">指定用于选择线程安全性选项的标志。</span><span class="sxs-lookup"><span data-stu-id="2782d-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="2782d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2782d-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="2782d-105">成员</span><span class="sxs-lookup"><span data-stu-id="2782d-105">Members</span></span>

|<span data-ttu-id="2782d-106">成员</span><span class="sxs-lookup"><span data-stu-id="2782d-106">Member</span></span>|<span data-ttu-id="2782d-107">描述</span><span class="sxs-lookup"><span data-stu-id="2782d-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="2782d-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="2782d-108">Default value.</span></span> <span data-ttu-id="2782d-109">与 `MDThreadSafetyOff` 相同。</span><span class="sxs-lookup"><span data-stu-id="2782d-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="2782d-110">指示不能设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="2782d-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="2782d-111">指示可以设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="2782d-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="2782d-112">要求</span><span class="sxs-lookup"><span data-stu-id="2782d-112">Requirements</span></span>

<span data-ttu-id="2782d-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2782d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2782d-114">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2782d-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="2782d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2782d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2782d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2782d-116">See also</span></span>

- [<span data-ttu-id="2782d-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2782d-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
