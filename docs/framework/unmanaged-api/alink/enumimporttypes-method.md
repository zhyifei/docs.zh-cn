---
title: EnumImportTypes 方法
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789950"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="bd7bd-102">EnumImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="bd7bd-102">EnumImportTypes Method</span></span>

<span data-ttu-id="bd7bd-103">枚举每个作用域中的每个类型。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd7bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd7bd-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="bd7bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd7bd-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="bd7bd-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="bd7bd-107">要检索的类型的最大数目。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="bd7bd-108">收到令牌类型，不能超过`dwMax`。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="bd7bd-109">接收中的类型的实际数目`aTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="bd7bd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bd7bd-110">Return Value</span></span>

<span data-ttu-id="bd7bd-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bd7bd-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd7bd-112">要求</span><span class="sxs-lookup"><span data-stu-id="bd7bd-112">Requirements</span></span>

<span data-ttu-id="bd7bd-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="bd7bd-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="bd7bd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd7bd-114">See also</span></span>

- [<span data-ttu-id="bd7bd-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="bd7bd-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bd7bd-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="bd7bd-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bd7bd-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="bd7bd-117">ALink API</span></span>](index.md)