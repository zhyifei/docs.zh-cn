---
title: ExportType 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226912"
---
# <a name="exporttype-method"></a><span data-ttu-id="df77a-102">ExportType 方法</span><span class="sxs-lookup"><span data-stu-id="df77a-102">ExportType Method</span></span>
<span data-ttu-id="df77a-103">指定的类型是可导出。</span><span class="sxs-lookup"><span data-stu-id="df77a-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df77a-104">语法</span><span class="sxs-lookup"><span data-stu-id="df77a-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="df77a-105">参数</span><span class="sxs-lookup"><span data-stu-id="df77a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="df77a-106">要从导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="df77a-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="df77a-107">定义可导出的类型的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="df77a-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="df77a-108">标记要成为可导出的类型。</span><span class="sxs-lookup"><span data-stu-id="df77a-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="df77a-109">要成为可导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="df77a-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 `ComType` <span data-ttu-id="df77a-110">标志，如`tdPublic`或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="df77a-110">flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="df77a-111">此参数可能会传递到[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="df77a-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="df77a-112">接收导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="df77a-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df77a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="df77a-113">Return Value</span></span>  
 <span data-ttu-id="df77a-114">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="df77a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df77a-115">要求</span><span class="sxs-lookup"><span data-stu-id="df77a-115">Requirements</span></span>  
 <span data-ttu-id="df77a-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="df77a-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df77a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="df77a-117">See also</span></span>

- [<span data-ttu-id="df77a-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="df77a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="df77a-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="df77a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="df77a-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="df77a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
