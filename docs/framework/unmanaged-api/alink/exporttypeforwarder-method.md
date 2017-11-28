---
title: "ExportTypeForwarder 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportTypeForwarder
helpviewer_keywords: ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f117d64673729113d917d700e3a26f9723b5a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="937c8-102">ExportTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="937c8-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="937c8-103">将类型转发器添加到给定的程序集的类型表。</span><span class="sxs-lookup"><span data-stu-id="937c8-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="937c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="937c8-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="937c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="937c8-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="937c8-106">类型转发器所引用的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="937c8-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="937c8-107">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="937c8-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="937c8-108">`ComType`标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="937c8-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="937c8-109">此值可能会传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="937c8-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="937c8-110">收到的导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="937c8-110">Receives the token of the exported type.</span></span> <span data-ttu-id="937c8-111">这是只需将发出嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="937c8-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="937c8-112">返回值</span><span class="sxs-lookup"><span data-stu-id="937c8-112">Return Value</span></span>  
 <span data-ttu-id="937c8-113">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="937c8-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="937c8-114">要求</span><span class="sxs-lookup"><span data-stu-id="937c8-114">Requirements</span></span>  
 <span data-ttu-id="937c8-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="937c8-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937c8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="937c8-116">See Also</span></span>  
 [<span data-ttu-id="937c8-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="937c8-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="937c8-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="937c8-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="937c8-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="937c8-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
