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
ms.openlocfilehash: d4b7064b0339825c29e4001bc35c4a604098468a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446496"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="1bbdf-102">EmitInternalExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="1bbdf-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="1bbdf-103">发出添加到程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="1bbdf-103">Emits types added to the assembly.</span></span> <span data-ttu-id="1bbdf-104">添加已知的内部类型后，调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1bbdf-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbdf-105">语法</span><span class="sxs-lookup"><span data-stu-id="1bbdf-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bbdf-106">参数</span><span class="sxs-lookup"><span data-stu-id="1bbdf-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1bbdf-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="1bbdf-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bbdf-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1bbdf-108">Return Value</span></span>  
 <span data-ttu-id="1bbdf-109">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1bbdf-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bbdf-110">要求</span><span class="sxs-lookup"><span data-stu-id="1bbdf-110">Requirements</span></span>  
 <span data-ttu-id="1bbdf-111">需要 alink</span><span class="sxs-lookup"><span data-stu-id="1bbdf-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbdf-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bbdf-112">See also</span></span>

- [<span data-ttu-id="1bbdf-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="1bbdf-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1bbdf-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="1bbdf-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1bbdf-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="1bbdf-115">ALink API</span></span>](index.md)
