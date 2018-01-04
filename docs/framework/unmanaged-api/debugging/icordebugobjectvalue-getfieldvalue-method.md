---
title: "ICorDebugObjectValue::GetFieldValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fcf53610cf96ef1ab62b4768521e8a2fb7ee6c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="4e873-102">ICorDebugObjectValue::GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e873-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="4e873-103">获取此对象值的指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="4e873-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e873-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e873-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e873-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e873-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="4e873-106">[in]指向一个表示要为其获取字段值的类的"ICorDebugClass"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4e873-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="4e873-107">[in]`mdFieldDef`引用描述字段的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="4e873-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4e873-108">[out]指向一个表示指定的字段的值的"ICorDebugValue"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4e873-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e873-109">备注</span><span class="sxs-lookup"><span data-stu-id="4e873-109">Remarks</span></span>  
 <span data-ttu-id="4e873-110">在指定的类`pClass`对象值的类的层次结构中必须是参数，并且该字段必须为该类的字段。</span><span class="sxs-lookup"><span data-stu-id="4e873-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="4e873-111">`GetFieldValue`方法为泛型对象和泛型类仍会成功。</span><span class="sxs-lookup"><span data-stu-id="4e873-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="4e873-112">例如，如果 MyDictionary\<V > 继承自字典\<字符串，V >，并且对象值的类型 MyDictionary\<int32 >，并传递`ICorDebugClass`字典的对象\<K，V > 将已成功获取字典中的字段\<字符串、 int32 >。</span><span class="sxs-lookup"><span data-stu-id="4e873-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e873-113">惠?</span><span class="sxs-lookup"><span data-stu-id="4e873-113">Requirements</span></span>  
 <span data-ttu-id="4e873-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e873-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e873-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e873-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e873-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e873-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e873-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e873-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e873-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e873-118">See Also</span></span>  
    
 
