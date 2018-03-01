---
title: "ImportTypes2 方法"
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
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47c49253a1e2839939ef4e671f155e4a44d07529
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="importtypes2-method"></a><span data-ttu-id="83cda-102">ImportTypes2 方法</span><span class="sxs-lookup"><span data-stu-id="83cda-102">ImportTypes2 Method</span></span>
<span data-ttu-id="83cda-103">启动导入的类型。</span><span class="sxs-lookup"><span data-stu-id="83cda-103">Initiates the import of types.</span></span> <span data-ttu-id="83cda-104">调用此方法可开始从通过导入每个作用域导入类型[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="83cda-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cda-105">语法</span><span class="sxs-lookup"><span data-stu-id="83cda-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83cda-106">参数</span><span class="sxs-lookup"><span data-stu-id="83cda-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="83cda-107">要导入到其中的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="83cda-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="83cda-108">要从中导入到的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="83cda-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="83cda-109">要从中导入的从零开始作用域。</span><span class="sxs-lookup"><span data-stu-id="83cda-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="83cda-110">接收给定范围中的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="83cda-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="83cda-111">（可选） 接收[IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="83cda-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="83cda-112">（可选） 指定范围内接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="83cda-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83cda-113">返回值</span><span class="sxs-lookup"><span data-stu-id="83cda-113">Return Value</span></span>  
 <span data-ttu-id="83cda-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="83cda-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83cda-115">惠?</span><span class="sxs-lookup"><span data-stu-id="83cda-115">Requirements</span></span>  
 <span data-ttu-id="83cda-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="83cda-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cda-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="83cda-117">See Also</span></span>  
 [<span data-ttu-id="83cda-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="83cda-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="83cda-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="83cda-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="83cda-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="83cda-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
