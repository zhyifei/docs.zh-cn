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
ms.openlocfilehash: 55b9d185804f25c7431f2696d67753cc3ba02d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402036"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="573d7-102">EmitInternalExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="573d7-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="573d7-103">发出类型添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="573d7-103">Emits types added to the assembly.</span></span> <span data-ttu-id="573d7-104">调用此方法后已知已添加的内部类型。</span><span class="sxs-lookup"><span data-stu-id="573d7-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573d7-105">语法</span><span class="sxs-lookup"><span data-stu-id="573d7-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="573d7-106">参数</span><span class="sxs-lookup"><span data-stu-id="573d7-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="573d7-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="573d7-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="573d7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="573d7-108">Return Value</span></span>  
 <span data-ttu-id="573d7-109">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="573d7-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573d7-110">要求</span><span class="sxs-lookup"><span data-stu-id="573d7-110">Requirements</span></span>  
 <span data-ttu-id="573d7-111">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="573d7-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573d7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="573d7-112">See Also</span></span>  
 [<span data-ttu-id="573d7-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="573d7-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="573d7-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="573d7-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="573d7-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="573d7-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
