---
title: "EmitInternalExportedTypes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location: alink.dll
api_type: COM
f1_keywords: EmitInternalExportedTypes
helpviewer_keywords: EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48ad5e34b926cf3dab562f57bb9206fa0ba70e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="d432e-102">EmitInternalExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="d432e-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="d432e-103">发出类型添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="d432e-103">Emits types added to the assembly.</span></span> <span data-ttu-id="d432e-104">调用此方法后已知已添加的内部类型。</span><span class="sxs-lookup"><span data-stu-id="d432e-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d432e-105">语法</span><span class="sxs-lookup"><span data-stu-id="d432e-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d432e-106">参数</span><span class="sxs-lookup"><span data-stu-id="d432e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d432e-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="d432e-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d432e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d432e-108">Return Value</span></span>  
 <span data-ttu-id="d432e-109">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d432e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d432e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="d432e-110">Requirements</span></span>  
 <span data-ttu-id="d432e-111">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="d432e-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d432e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d432e-112">See Also</span></span>  
 [<span data-ttu-id="d432e-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="d432e-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d432e-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="d432e-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d432e-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="d432e-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
