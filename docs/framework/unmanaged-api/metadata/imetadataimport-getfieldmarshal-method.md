---
title: IMetaDataImport::GetFieldMarshal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175390"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="07e41-102">IMetaDataImport::GetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="07e41-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="07e41-103">获取指向指定字段元数据令牌表示的字段的本机非托管类型的指针。</span><span class="sxs-lookup"><span data-stu-id="07e41-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e41-104">语法</span><span class="sxs-lookup"><span data-stu-id="07e41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07e41-105">parameters</span><span class="sxs-lookup"><span data-stu-id="07e41-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="07e41-106">[在]表示获取内部封送信息的字段的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="07e41-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="07e41-107">[出]指向字段本机类型的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="07e41-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="07e41-108">[出]的大小（以字节为单位）。 `ppvNativeType`</span><span class="sxs-lookup"><span data-stu-id="07e41-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e41-109">要求</span><span class="sxs-lookup"><span data-stu-id="07e41-109">Requirements</span></span>  
 <span data-ttu-id="07e41-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07e41-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e41-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="07e41-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07e41-112">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="07e41-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07e41-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e41-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07e41-114">See also</span></span>

- [<span data-ttu-id="07e41-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="07e41-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="07e41-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="07e41-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
