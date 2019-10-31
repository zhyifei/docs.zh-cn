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
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095883"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="ea218-102">ICorDebugObjectValue::GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="ea218-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="ea218-103">获取此对象值的指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="ea218-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea218-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea218-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea218-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea218-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="ea218-106">中一个指向 "ICorDebugClass" 对象的指针，该对象表示要获取其字段值的类。</span><span class="sxs-lookup"><span data-stu-id="ea218-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="ea218-107">中一个 `mdFieldDef` 标记，它引用描述字段的元数据。</span><span class="sxs-lookup"><span data-stu-id="ea218-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ea218-108">弄一个指向 "ICorDebugValue" 对象的指针，该对象表示指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="ea218-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea218-109">备注</span><span class="sxs-lookup"><span data-stu-id="ea218-109">Remarks</span></span>  
 <span data-ttu-id="ea218-110">在 `pClass` 参数中指定的类必须位于对象值的类的层次结构中，并且字段必须是该类的字段。</span><span class="sxs-lookup"><span data-stu-id="ea218-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="ea218-111">对于泛型对象和泛型类，`GetFieldValue` 方法仍将成功。</span><span class="sxs-lookup"><span data-stu-id="ea218-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="ea218-112">例如，如果 MyDictionary\<V > 从字典继承\<string，V >，并且对象值的类型为 MyDictionary\<int32 >，则为字典传递 `ICorDebugClass` 对象\<K，V > 将成功获取的字段字典\<字符串，int32 >。</span><span class="sxs-lookup"><span data-stu-id="ea218-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea218-113">要求</span><span class="sxs-lookup"><span data-stu-id="ea218-113">Requirements</span></span>  
 <span data-ttu-id="ea218-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea218-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea218-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea218-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea218-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea218-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea218-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea218-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea218-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea218-118">See also</span></span>
