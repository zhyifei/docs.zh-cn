---
title: ImportTypes2 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51c696679626a598be422376e9dc89b5add1773d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400486"
---
# <a name="importtypes2-method"></a><span data-ttu-id="34abb-102">ImportTypes2 方法</span><span class="sxs-lookup"><span data-stu-id="34abb-102">ImportTypes2 Method</span></span>
<span data-ttu-id="34abb-103">启动导入的类型。</span><span class="sxs-lookup"><span data-stu-id="34abb-103">Initiates the import of types.</span></span> <span data-ttu-id="34abb-104">调用此方法可开始从通过导入每个作用域导入类型[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="34abb-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34abb-105">语法</span><span class="sxs-lookup"><span data-stu-id="34abb-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="34abb-106">参数</span><span class="sxs-lookup"><span data-stu-id="34abb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="34abb-107">要导入到其中的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="34abb-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="34abb-108">要从中导入到的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="34abb-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="34abb-109">要从中导入的从零开始作用域。</span><span class="sxs-lookup"><span data-stu-id="34abb-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="34abb-110">接收给定范围中的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="34abb-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="34abb-111">（可选） 接收[IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="34abb-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="34abb-112">（可选） 指定范围内接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="34abb-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34abb-113">返回值</span><span class="sxs-lookup"><span data-stu-id="34abb-113">Return Value</span></span>  
 <span data-ttu-id="34abb-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="34abb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34abb-115">要求</span><span class="sxs-lookup"><span data-stu-id="34abb-115">Requirements</span></span>  
 <span data-ttu-id="34abb-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="34abb-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34abb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="34abb-117">See Also</span></span>  
 [<span data-ttu-id="34abb-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="34abb-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="34abb-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="34abb-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="34abb-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="34abb-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
