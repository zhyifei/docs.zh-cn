---
title: "ImportTypes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="f611e-102">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="f611e-102">ImportTypes Method</span></span>
<span data-ttu-id="f611e-103">启动从通过导入每个作用域的类型的导入[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f611e-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f611e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f611e-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f611e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f611e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f611e-106">要导入到的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f611e-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f611e-107">要从中导入的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="f611e-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f611e-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="f611e-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="f611e-109">接收此范围中的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="f611e-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f611e-110">（可选） 接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f611e-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="f611e-111">（可选） 指定范围内接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="f611e-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f611e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f611e-112">Return Value</span></span>  
 <span data-ttu-id="f611e-113">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f611e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f611e-114">要求</span><span class="sxs-lookup"><span data-stu-id="f611e-114">Requirements</span></span>  
 <span data-ttu-id="f611e-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="f611e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f611e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f611e-116">See Also</span></span>  
 [<span data-ttu-id="f611e-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f611e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f611e-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f611e-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f611e-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="f611e-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
