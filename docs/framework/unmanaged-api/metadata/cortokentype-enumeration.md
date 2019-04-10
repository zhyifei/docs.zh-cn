---
title: CorTokenType 枚举
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230507"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="950f7-102">CorTokenType 枚举</span><span class="sxs-lookup"><span data-stu-id="950f7-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="950f7-103">指示元数据标记的类型。</span><span class="sxs-lookup"><span data-stu-id="950f7-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="950f7-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="950f7-105">成员</span><span class="sxs-lookup"><span data-stu-id="950f7-105">Members</span></span>  
  
|<span data-ttu-id="950f7-106">成员</span><span class="sxs-lookup"><span data-stu-id="950f7-106">Member</span></span>|<span data-ttu-id="950f7-107">描述</span><span class="sxs-lookup"><span data-stu-id="950f7-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="950f7-108">`mdModule`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="950f7-109">`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="950f7-110">`mdTypeDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="950f7-111">`mdFieldDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="950f7-112">`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="950f7-113">`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="950f7-114">`mdInterfaceImpl`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="950f7-115">`mdMemberRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="950f7-116">`mdCustomAttribute`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="950f7-117">`mdPermission`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="950f7-118">`mdSignature`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="950f7-119">`mdEvent`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="950f7-120">`mdProperty`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="950f7-121">`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="950f7-122">`mdTypeSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="950f7-123">`mdAssembly`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="950f7-124">`mdAssemblyRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="950f7-125">`mdFile`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="950f7-126">`mdExportedType`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="950f7-127">`mdManifestResource`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="950f7-128">`mdGenericParam`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="950f7-129">`mdMethodSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="950f7-130">`mdGenericParamConstraint`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="950f7-131">`mdString`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="950f7-132">`mdName`令牌。</span><span class="sxs-lookup"><span data-stu-id="950f7-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="950f7-133">未使用。</span><span class="sxs-lookup"><span data-stu-id="950f7-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="950f7-134">备注</span><span class="sxs-lookup"><span data-stu-id="950f7-134">Remarks</span></span>  
 <span data-ttu-id="950f7-135">每个值是相应的元数据令牌中的最高位字节的值相等。</span><span class="sxs-lookup"><span data-stu-id="950f7-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950f7-136">要求</span><span class="sxs-lookup"><span data-stu-id="950f7-136">Requirements</span></span>  
 <span data-ttu-id="950f7-137">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="950f7-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950f7-138">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="950f7-138">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="950f7-139">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="950f7-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="950f7-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="950f7-140">See also</span></span>

- [<span data-ttu-id="950f7-141">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="950f7-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
