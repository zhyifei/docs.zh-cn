---
title: CorNativeType 枚举
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: 09a351db65c7ed310d3eb68c71a5207ed6040dd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177974"
---
# <a name="cornativetype-enumeration"></a>CorNativeType 枚举
包含一些值，用于描述本机非托管类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|已过时。|  
|`NATIVE_TYPE_VOID`|已过时。|  
|`NATIVE_TYPE_BOOLEAN`|4 字节布尔值，其中 TRUE 为非零，FALSE 为零。|  
|`NATIVE_TYPE_I1`|已签名的 8 位整数值。|  
|`NATIVE_TYPE_U1`|未签名的 8 位整数值。|  
|`NATIVE_TYPE_I2`|已签名的 16 位整数值。|  
|`NATIVE_TYPE_U2`|未签名的 16 位整数值。|  
|`NATIVE_TYPE_I4`|带符号的 32 位整数值。|  
|`NATIVE_TYPE_U4`|32 位无符号整数值。|  
|`NATIVE_TYPE_I8`|已签名的 64 位整数值。|  
|`NATIVE_TYPE_U8`|未签名的 64 位整数值。|  
|`NATIVE_TYPE_R4`|4 字节浮点数值。|  
|`NATIVE_TYPE_R8`|8 字节浮点数值。|  
|`NATIVE_TYPE_SYSCHAR`|已过时。|  
|`NATIVE_TYPE_VARIANT`|已过时。|  
|`NATIVE_TYPE_CURRENCY`|对应于托管<xref:System.Decimal>类型的数字 COM 类型。|  
|`NATIVE_TYPE_PTR`|已过时。|  
|`NATIVE_TYPE_DECIMAL`|已过时。|  
|`NATIVE_TYPE_DATE`|已过时。|  
|`NATIVE_TYPE_BSTR`|COM 互操作。|  
|`NATIVE_TYPE_LPSTR`|LPSTR 字符串值。|  
|`NATIVE_TYPE_LPWSTR`|LPWSTR 字符串值。|  
|`NATIVE_TYPE_LPTSTR`|LPTSTR 字符串值。|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|固定的系统定义的字符串值。|  
|`NATIVE_TYPE_OBJECTREF`|已过时。|  
|`NATIVE_TYPE_IUNKNOWN`|COM 互操作。|  
|`NATIVE_TYPE_IDISPATCH`|COM 互操作。|  
|`NATIVE_TYPE_STRUCT`|本机结构值。|  
|`NATIVE_TYPE_INTF`|COM 互操作。|  
|`NATIVE_TYPE_SAFEARRAY`|COM 互操作。|  
|`NATIVE_TYPE_FIXEDARRAY`|固定长度数组值。|  
|`NATIVE_TYPE_INT`|本机 16 位签名整数值。|  
|`NATIVE_TYPE_UINT`|本机 16 位无符号整数值。|  
|`NATIVE_TYPE_NESTEDSTRUCT`|已过时。<br /><br /> 使用NATIVE_TYPE_STRUCT。|  
|`NATIVE_TYPE_BYVALSTR`|COM 互操作。|  
|`NATIVE_TYPE_ANSIBSTR`|COM 互操作。|  
|`NATIVE_TYPE_TBSTR`|COM 互操作。<br /><br /> 根据平台选择 BSTR 或 ANSIBSTR。|  
|`NATIVE_TYPE_VARIANTBOOL`|2 字节布尔值，其中 TRUE 为 -1，FALSE 为零。|  
|`NATIVE_TYPE_FUNC`|函数指针。|  
|`NATIVE_TYPE_ASANY`|对任何本机类型的引用。|  
|`NATIVE_TYPE_ARRAY`|对具有未指定类型成员的数组的引用。|  
|`NATIVE_TYPE_LPSTRUCT`|指向结构的 32 位整数指针。|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|自定义封送器本机类型。<br /><br /> 之后必须使用以下格式的字符串："本机类型名称/0自定义封送器类型名称/0可选 Cookie/0"或"{本机类型 GUID}/0自定义封送器类型名称/0 可选 Cookie/0"|  
|`NATIVE_TYPE_ERROR`|COM 互操作。<br /><br /> 使用ELEMENT_TYPE_I4此类型映射到VT_HRESULT。|  
|`NATIVE_TYPE_IINSPECTABLE`|本机`IInspectable`类型。|  
|`NATIVE_TYPE_HSTRING`|本机`HString`。|  
|`NATIVE_TYPE_MAX`|一个无效值。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫德  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
