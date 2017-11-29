---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="24dfb-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="24dfb-102">GetScope Method1</span></span>
<span data-ttu-id="24dfb-103">获取导入作用域。</span><span class="sxs-lookup"><span data-stu-id="24dfb-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24dfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="24dfb-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24dfb-105">参数</span><span class="sxs-lookup"><span data-stu-id="24dfb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="24dfb-106">要导入到程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="24dfb-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="24dfb-107">唯一的文件 ID 从导入。</span><span class="sxs-lookup"><span data-stu-id="24dfb-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="24dfb-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="24dfb-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="24dfb-109">接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="24dfb-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24dfb-110">返回值</span><span class="sxs-lookup"><span data-stu-id="24dfb-110">Return Value</span></span>  
 <span data-ttu-id="24dfb-111">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="24dfb-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24dfb-112">要求</span><span class="sxs-lookup"><span data-stu-id="24dfb-112">Requirements</span></span>  
 <span data-ttu-id="24dfb-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="24dfb-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24dfb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24dfb-114">See Also</span></span>  
 [<span data-ttu-id="24dfb-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="24dfb-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="24dfb-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="24dfb-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="24dfb-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="24dfb-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
