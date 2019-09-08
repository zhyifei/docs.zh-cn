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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d8827f46a12bd090fa27e71072d833607d34677
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777350"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="ca80c-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="ca80c-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="ca80c-103">检索程序集级别的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="ca80c-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca80c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca80c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca80c-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca80c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ca80c-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="ca80c-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ca80c-107">要枚举的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="ca80c-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="ca80c-108">`mdTokenNill`用于所有属性。</span><span class="sxs-lookup"><span data-stu-id="ca80c-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="ca80c-109">接收自定义特性标记。</span><span class="sxs-lookup"><span data-stu-id="ca80c-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ca80c-110">指定数组的`rCustomValues`大小。</span><span class="sxs-lookup"><span data-stu-id="ca80c-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="ca80c-111">可以选择接收令牌值的计数。</span><span class="sxs-lookup"><span data-stu-id="ca80c-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca80c-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ca80c-112">Return Value</span></span>  
 <span data-ttu-id="ca80c-113">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ca80c-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca80c-114">要求</span><span class="sxs-lookup"><span data-stu-id="ca80c-114">Requirements</span></span>  
 <span data-ttu-id="ca80c-115">需要 alink</span><span class="sxs-lookup"><span data-stu-id="ca80c-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca80c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca80c-116">See also</span></span>

- [<span data-ttu-id="ca80c-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="ca80c-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ca80c-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="ca80c-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ca80c-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="ca80c-119">ALink API</span></span>](index.md)
