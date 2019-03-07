---
title: SetAssemblyFile2 方法
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41e10855a7254da4124ac0bf9aa247b90311632b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479072"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="d6c9f-102">SetAssemblyFile2 方法</span><span class="sxs-lookup"><span data-stu-id="d6c9f-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="d6c9f-103">设置的名称和新的程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="d6c9f-104">当生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c9f-105">语法</span><span class="sxs-lookup"><span data-stu-id="d6c9f-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6c9f-106">参数</span><span class="sxs-lookup"><span data-stu-id="d6c9f-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d6c9f-107">清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="d6c9f-108">[IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)此文件的接口。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="d6c9f-109">所表示的选项[AssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="d6c9f-110">接收有关正在构造的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6c9f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d6c9f-111">Return Value</span></span>  
 <span data-ttu-id="d6c9f-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c9f-113">要求</span><span class="sxs-lookup"><span data-stu-id="d6c9f-113">Requirements</span></span>  
 <span data-ttu-id="d6c9f-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="d6c9f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c9f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6c9f-115">See also</span></span>
- [<span data-ttu-id="d6c9f-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="d6c9f-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d6c9f-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="d6c9f-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d6c9f-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="d6c9f-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
