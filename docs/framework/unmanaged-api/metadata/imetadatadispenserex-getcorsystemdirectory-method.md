---
title: IMetaDataDispenserEx::GetCORSystemDirectory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: a76c17e663fdf6555ed878cca1b86b6a9395730e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008789"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a>IMetaDataDispenserEx::GetCORSystemDirectory 方法
获取保存当前公共语言运行时（CLR）的目录。 此方法仅支持在进程外调试器中使用。 如果从另一个组件调用，它将返回 E_NOTIMPL。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a>参数  
 `szBuffer`  
 弄要接收目录名称的缓冲区。  
  
 `cchBuffer`  
 中的大小（以字节为单位） `szBuffer` 。  
  
 `pchBuffer`  
 弄中实际返回的字节数 `szBuffer` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataDispenserEx 接口](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 接口](imetadatadispenser-interface.md)
