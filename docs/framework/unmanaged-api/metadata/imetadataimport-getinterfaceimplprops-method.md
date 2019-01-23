---
title: IMetaDataImport::GetInterfaceImplProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91cb42a5bf1115de82b5fe28693cb77b66915c9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600552"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="af1cc-102">IMetaDataImport::GetInterfaceImplProps 方法</span><span class="sxs-lookup"><span data-stu-id="af1cc-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="af1cc-103">获取一个指针指向的元数据令牌<xref:System.Type>实现指定的方法和接口，其用于声明该方法。</span><span class="sxs-lookup"><span data-stu-id="af1cc-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="af1cc-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af1cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="af1cc-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="af1cc-106">[in]表示此方法返回的类和接口令牌的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="af1cc-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="af1cc-107">[out]表示实现方法的类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="af1cc-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="af1cc-108">[out]表示定义实现的方法的接口的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="af1cc-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af1cc-109">要求</span><span class="sxs-lookup"><span data-stu-id="af1cc-109">Requirements</span></span>  
 <span data-ttu-id="af1cc-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af1cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af1cc-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af1cc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af1cc-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="af1cc-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af1cc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af1cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1cc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="af1cc-114">See also</span></span>
- [<span data-ttu-id="af1cc-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="af1cc-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="af1cc-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="af1cc-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
