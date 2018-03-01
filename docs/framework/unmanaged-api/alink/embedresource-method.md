---
title: "EmbedResource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 815e4b6abbb56b0998a12c096f0ba7cb678778ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="036ca-102">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="036ca-102">EmbedResource Method</span></span>
<span data-ttu-id="036ca-103">声明嵌入的资源。</span><span class="sxs-lookup"><span data-stu-id="036ca-103">Declares an embedded resource.</span></span> <span data-ttu-id="036ca-104">此方法不会实际嵌入资源。</span><span class="sxs-lookup"><span data-stu-id="036ca-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="036ca-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="036ca-106">参数</span><span class="sxs-lookup"><span data-stu-id="036ca-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="036ca-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="036ca-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="036ca-108">包含资源的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="036ca-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="036ca-109">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="036ca-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="036ca-110">来自 RVA 的资源的偏移量。</span><span class="sxs-lookup"><span data-stu-id="036ca-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="036ca-111">可访问性标志，如`mrPublic`和`mrPrivate`。</span><span class="sxs-lookup"><span data-stu-id="036ca-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="036ca-112">这些标志可能传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="036ca-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="036ca-113">返回值</span><span class="sxs-lookup"><span data-stu-id="036ca-113">Return Value</span></span>  
 <span data-ttu-id="036ca-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="036ca-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="036ca-115">惠?</span><span class="sxs-lookup"><span data-stu-id="036ca-115">Requirements</span></span>  
 <span data-ttu-id="036ca-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="036ca-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036ca-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="036ca-117">See Also</span></span>  
 [<span data-ttu-id="036ca-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="036ca-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="036ca-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="036ca-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="036ca-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="036ca-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
