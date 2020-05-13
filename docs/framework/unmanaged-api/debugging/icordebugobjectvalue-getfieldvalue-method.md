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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207590"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="e2d56-102">ICorDebugObjectValue::GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="e2d56-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="e2d56-103">获取此对象值的指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="e2d56-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d56-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2d56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d56-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2d56-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e2d56-106">中一个指向 "ICorDebugClass" 对象的指针，该对象表示要获取其字段值的类。</span><span class="sxs-lookup"><span data-stu-id="e2d56-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="e2d56-107">中`mdFieldDef`引用描述字段的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="e2d56-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e2d56-108">弄一个指向 "ICorDebugValue" 对象的指针，该对象表示指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="e2d56-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d56-109">备注</span><span class="sxs-lookup"><span data-stu-id="e2d56-109">Remarks</span></span>  
 <span data-ttu-id="e2d56-110">参数中指定的类 `pClass` 必须位于对象值的类的层次结构中，并且字段必须是该类的字段。</span><span class="sxs-lookup"><span data-stu-id="e2d56-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="e2d56-111">`GetFieldValue`对于泛型对象和泛型类，该方法仍将成功。</span><span class="sxs-lookup"><span data-stu-id="e2d56-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="e2d56-112">例如，如果 MyDictionary \< V> 继承自字典 \< 字符串，V>，而对象值的类型为 MyDictionary \< int32>，则 `ICorDebugClass` 为字典 \< K，V> 传递对象将成功获取字典 \< 字符串 int32> 的字段。</span><span class="sxs-lookup"><span data-stu-id="e2d56-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d56-113">要求</span><span class="sxs-lookup"><span data-stu-id="e2d56-113">Requirements</span></span>  
 <span data-ttu-id="e2d56-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d56-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d56-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2d56-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2d56-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d56-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d56-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2d56-118">See also</span></span>
