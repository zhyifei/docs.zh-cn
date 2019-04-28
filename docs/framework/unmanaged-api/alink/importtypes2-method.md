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
ms.openlocfilehash: f14822a58f3982d6f9fee1328c10b960657c056f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753499"
---
# <a name="importtypes2-method"></a><span data-ttu-id="75ee6-102">ImportTypes2 方法</span><span class="sxs-lookup"><span data-stu-id="75ee6-102">ImportTypes2 Method</span></span>
<span data-ttu-id="75ee6-103">启动导入的类型。</span><span class="sxs-lookup"><span data-stu-id="75ee6-103">Initiates the import of types.</span></span> <span data-ttu-id="75ee6-104">调用此方法以开始从通过导入每个作用域导入类型[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="75ee6-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ee6-105">语法</span><span class="sxs-lookup"><span data-stu-id="75ee6-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="75ee6-106">参数</span><span class="sxs-lookup"><span data-stu-id="75ee6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="75ee6-107">要导入到其中的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="75ee6-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="75ee6-108">要从中导入到的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="75ee6-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="75ee6-109">要从中导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="75ee6-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="75ee6-110">在给定作用域中接收的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="75ee6-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="75ee6-111">可选择性地接收[IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="75ee6-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="75ee6-112">可选择性地指定作用域内接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="75ee6-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75ee6-113">返回值</span><span class="sxs-lookup"><span data-stu-id="75ee6-113">Return Value</span></span>  
 <span data-ttu-id="75ee6-114">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="75ee6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75ee6-115">要求</span><span class="sxs-lookup"><span data-stu-id="75ee6-115">Requirements</span></span>  
 <span data-ttu-id="75ee6-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="75ee6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ee6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="75ee6-117">See also</span></span>

- [<span data-ttu-id="75ee6-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="75ee6-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="75ee6-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="75ee6-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="75ee6-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="75ee6-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
