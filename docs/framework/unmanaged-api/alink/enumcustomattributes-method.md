---
title: EnumCustomAttributes 方法
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446476"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="fdfe3-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="fdfe3-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="fdfe3-103">Retrieves assembly-level custom attributes.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfe3-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdfe3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdfe3-105">参数</span><span class="sxs-lookup"><span data-stu-id="fdfe3-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="fdfe3-106">Handle of enumerator.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="fdfe3-107">Type of attributes to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="fdfe3-108">Use `mdTokenNill` for all attributes.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="fdfe3-109">Receives custom attributes tokens.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fdfe3-110">Specifies size of `rCustomValues` array.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="fdfe3-111">Optionally receives count of token values.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdfe3-112">返回值</span><span class="sxs-lookup"><span data-stu-id="fdfe3-112">Return Value</span></span>  
 <span data-ttu-id="fdfe3-113">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="fdfe3-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdfe3-114">要求</span><span class="sxs-lookup"><span data-stu-id="fdfe3-114">Requirements</span></span>  
 <span data-ttu-id="fdfe3-115">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="fdfe3-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfe3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdfe3-116">See also</span></span>

- [<span data-ttu-id="fdfe3-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="fdfe3-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fdfe3-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="fdfe3-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fdfe3-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="fdfe3-119">ALink API</span></span>](index.md)
