---
title: ICLRMetadataLocator::GetMetadata 方法
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: ad309290319396ff4e74e30d572effeffe802d1d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859879"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata 方法
由公共语言运行时（CLR）数据访问服务调用以检索图像的元数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `imagePath`  
 中一个字符串，指定图像文件的路径。  
  
 `imageTimestamp`  
 中图像文件的时间戳。  
  
 `imageSize`  
 中图像文件的大小。  
  
 `mvid`  
 中图像的全局唯一标识符。  
  
 `mdRva`  
 中元数据的相对虚拟地址（RVA）。 地址相对于映像基址。  
  
 `flags`  
 中保留供将来使用。  
  
 `bufferSize`  
 中要在其中放置元数据的缓冲区的大小。  
  
 `buffer`  
 弄要在其中放置元数据的缓冲区。  
  
 `dataSize`  
 弄返回的元数据的大小。  
  
## <a name="remarks"></a>备注  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** ClrData，ClrData  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRMetadataLocator 接口](iclrmetadatalocator-interface.md)
