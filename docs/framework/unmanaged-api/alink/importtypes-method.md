---
title: ImportTypes 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6591fb4a2b4944dc0d02f70f0f90ffd87e071c47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734995"
---
# <a name="importtypes-method"></a><span data-ttu-id="71448-102">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="71448-102">ImportTypes Method</span></span>
<span data-ttu-id="71448-103">启动导入的类型从通过导入每个作用域[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="71448-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71448-104">语法</span><span class="sxs-lookup"><span data-stu-id="71448-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="71448-105">参数</span><span class="sxs-lookup"><span data-stu-id="71448-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="71448-106">要导入到的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="71448-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="71448-107">若要从导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="71448-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="71448-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="71448-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="71448-109">在此作用域中接收的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="71448-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="71448-110">可选择性地接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="71448-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="71448-111">可选择性地指示作用域中接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="71448-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71448-112">返回值</span><span class="sxs-lookup"><span data-stu-id="71448-112">Return Value</span></span>  
 <span data-ttu-id="71448-113">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="71448-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71448-114">要求</span><span class="sxs-lookup"><span data-stu-id="71448-114">Requirements</span></span>  
 <span data-ttu-id="71448-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="71448-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71448-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="71448-116">See also</span></span>
- [<span data-ttu-id="71448-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="71448-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="71448-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="71448-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="71448-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="71448-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
