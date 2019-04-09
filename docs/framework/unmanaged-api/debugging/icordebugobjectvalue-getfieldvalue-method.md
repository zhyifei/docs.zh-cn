---
title: ICorDebugObjectValue::GetFieldValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8778edf9ac6e32d5dab3a53a6d9cc643a8df13b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107908"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="4342c-102">ICorDebugObjectValue::GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="4342c-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="4342c-103">获取此对象值的指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="4342c-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4342c-104">语法</span><span class="sxs-lookup"><span data-stu-id="4342c-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4342c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4342c-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="4342c-106">[in]指向"ICorDebugClass"对象，表示要为其获取字段值的类的指针。</span><span class="sxs-lookup"><span data-stu-id="4342c-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="4342c-107">[in]`mdFieldDef`引用描述字段的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="4342c-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4342c-108">[out]指向一个"ICorDebugValue"对象，表示指定字段的值的指针。</span><span class="sxs-lookup"><span data-stu-id="4342c-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4342c-109">备注</span><span class="sxs-lookup"><span data-stu-id="4342c-109">Remarks</span></span>  
 <span data-ttu-id="4342c-110">中指定类`pClass`参数，必须是对象值的类的层次结构中，此字段必须是该类的字段。</span><span class="sxs-lookup"><span data-stu-id="4342c-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="4342c-111">`GetFieldValue`方法仍将成功为泛型对象和泛型类。</span><span class="sxs-lookup"><span data-stu-id="4342c-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="4342c-112">例如，如果 MyDictionary\<V > 继承自字典\<字符串，V >，且对象值的类型 MyDictionary\<int32 >，并传递`ICorDebugClass`字典对象\<K，V > 将已成功获取字典中的字段\<string，int32 >。</span><span class="sxs-lookup"><span data-stu-id="4342c-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4342c-113">要求</span><span class="sxs-lookup"><span data-stu-id="4342c-113">Requirements</span></span>  
 <span data-ttu-id="4342c-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4342c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4342c-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4342c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4342c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4342c-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4342c-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4342c-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4342c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4342c-118">See also</span></span>
