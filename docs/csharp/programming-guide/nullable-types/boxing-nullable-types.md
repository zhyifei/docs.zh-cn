---
title: "装箱可以为 null 的类型（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 29fccba56f6758fdfd407fa1879baa9260b69187
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="35ef3-102">装箱可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="35ef3-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="35ef3-103">基于可以为 null 的类型的对象仅在其不为 null 时才可装箱。</span><span class="sxs-lookup"><span data-stu-id="35ef3-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="35ef3-104">如果 <xref:System.Nullable%601.HasValue%2A> 为 `false`，则对象引用将分配给 `null` 而不是进行装箱。</span><span class="sxs-lookup"><span data-stu-id="35ef3-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="35ef3-105">例如：</span><span class="sxs-lookup"><span data-stu-id="35ef3-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="35ef3-106">假如对象为非 null，即如果 <xref:System.Nullable%601.HasValue%2A> 为 `true`，则将发生装箱，但仅装箱可以为 null 的对象所基于的基础类型。</span><span class="sxs-lookup"><span data-stu-id="35ef3-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="35ef3-107">装箱某个可以为 null 的非 null 值类型将装箱该值类型本身，而不是包装该值类型的 <xref:System.Nullable%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="35ef3-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=nameWithType> that wraps the value type.</span></span> <span data-ttu-id="35ef3-108">例如：</span><span class="sxs-lookup"><span data-stu-id="35ef3-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="35ef3-109">两个已装箱的对象与通过装箱不可为 null 的类型所创建的对象相同。</span><span class="sxs-lookup"><span data-stu-id="35ef3-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="35ef3-110">并且，与不可以为 null 的装箱类型一样，可将其取消装箱为可为 null 的类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="35ef3-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="35ef3-111">备注</span><span class="sxs-lookup"><span data-stu-id="35ef3-111">Remarks</span></span>  
 <span data-ttu-id="35ef3-112">可以为 null 的类型在装箱时的行为可提供两大好处：</span><span class="sxs-lookup"><span data-stu-id="35ef3-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="35ef3-113">可以为 null 的对象和其装箱的对应项可进行 null 测试：</span><span class="sxs-lookup"><span data-stu-id="35ef3-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  <span data-ttu-id="35ef3-114">装箱的可以为 null 的类型完全支持基础类型的功能：</span><span class="sxs-lookup"><span data-stu-id="35ef3-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="35ef3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35ef3-115">See Also</span></span>  
 [<span data-ttu-id="35ef3-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="35ef3-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="35ef3-117">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="35ef3-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="35ef3-118">如何：标识可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="35ef3-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
