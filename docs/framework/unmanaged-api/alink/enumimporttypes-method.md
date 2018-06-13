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
ms.openlocfilehash: 90319886dfe149a3d2d76451c1a8526299cf5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401643"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="73d7e-102">EnumImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="73d7e-102">EnumImportTypes Method</span></span>
<span data-ttu-id="73d7e-103">枚举中每个作用域的每个类型。</span><span class="sxs-lookup"><span data-stu-id="73d7e-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d7e-104">语法</span><span class="sxs-lookup"><span data-stu-id="73d7e-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73d7e-105">参数</span><span class="sxs-lookup"><span data-stu-id="73d7e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="73d7e-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="73d7e-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="73d7e-107">要检索的类型的最大数量。</span><span class="sxs-lookup"><span data-stu-id="73d7e-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="73d7e-108">接收类型标记，不能超过`dwMax`。</span><span class="sxs-lookup"><span data-stu-id="73d7e-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="73d7e-109">接收的类型中实际数`aTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="73d7e-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73d7e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="73d7e-110">Return Value</span></span>  
 <span data-ttu-id="73d7e-111">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="73d7e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d7e-112">要求</span><span class="sxs-lookup"><span data-stu-id="73d7e-112">Requirements</span></span>  
 <span data-ttu-id="73d7e-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="73d7e-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d7e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="73d7e-114">See Also</span></span>  
 [<span data-ttu-id="73d7e-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="73d7e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="73d7e-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="73d7e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="73d7e-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="73d7e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
