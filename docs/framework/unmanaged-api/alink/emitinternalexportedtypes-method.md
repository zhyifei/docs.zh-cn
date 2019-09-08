---
title: EmitInternalExportedTypes 方法
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04103ad305e0ae97669f3e07e06f03c2cdb4dfbd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787518"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="b5dd5-102">EmitInternalExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="b5dd5-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="b5dd5-103">发出添加到程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="b5dd5-103">Emits types added to the assembly.</span></span> <span data-ttu-id="b5dd5-104">添加已知的内部类型后，调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b5dd5-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5dd5-105">语法</span><span class="sxs-lookup"><span data-stu-id="b5dd5-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5dd5-106">参数</span><span class="sxs-lookup"><span data-stu-id="b5dd5-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b5dd5-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="b5dd5-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5dd5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b5dd5-108">Return Value</span></span>  
 <span data-ttu-id="b5dd5-109">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b5dd5-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5dd5-110">要求</span><span class="sxs-lookup"><span data-stu-id="b5dd5-110">Requirements</span></span>  
 <span data-ttu-id="b5dd5-111">需要 alink</span><span class="sxs-lookup"><span data-stu-id="b5dd5-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5dd5-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5dd5-112">See also</span></span>

- [<span data-ttu-id="b5dd5-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="b5dd5-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b5dd5-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b5dd5-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b5dd5-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="b5dd5-115">ALink API</span></span>](index.md)
