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
ms.openlocfilehash: c196bcc159b18b9dc04329d817ebe16e07bb8bb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790008"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="f81ab-102">EmitInternalExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="f81ab-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="f81ab-103">发出类型添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="f81ab-103">Emits types added to the assembly.</span></span> <span data-ttu-id="f81ab-104">调用此方法后添加内部类型已知。</span><span class="sxs-lookup"><span data-stu-id="f81ab-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81ab-105">语法</span><span class="sxs-lookup"><span data-stu-id="f81ab-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f81ab-106">参数</span><span class="sxs-lookup"><span data-stu-id="f81ab-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f81ab-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f81ab-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f81ab-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f81ab-108">Return Value</span></span>  
 <span data-ttu-id="f81ab-109">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f81ab-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f81ab-110">要求</span><span class="sxs-lookup"><span data-stu-id="f81ab-110">Requirements</span></span>  
 <span data-ttu-id="f81ab-111">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="f81ab-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81ab-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f81ab-112">See also</span></span>

- [<span data-ttu-id="f81ab-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f81ab-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f81ab-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f81ab-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f81ab-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="f81ab-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
