---
title: 装箱可以为 null 的类型（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334751"
---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="e56f1-102">装箱可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e56f1-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="e56f1-103">基于可以为 null 的类型的对象仅在其不为 null 时才可装箱。</span><span class="sxs-lookup"><span data-stu-id="e56f1-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="e56f1-104">如果 <xref:System.Nullable%601.HasValue%2A> 为 `false`，则对象引用将分配给 `null` 而不是进行装箱。</span><span class="sxs-lookup"><span data-stu-id="e56f1-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="e56f1-105">例如:</span><span class="sxs-lookup"><span data-stu-id="e56f1-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="e56f1-106">假如对象为非 null，即如果 <xref:System.Nullable%601.HasValue%2A> 为 `true`，则将发生装箱，但仅装箱可以为 null 的对象所基于的基础类型。</span><span class="sxs-lookup"><span data-stu-id="e56f1-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="e56f1-107">装箱某个可以为 null 的非 null 值类型将装箱该值类型本身，而不是包装该值类型的 <xref:System.Nullable%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e56f1-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=nameWithType> that wraps the value type.</span></span> <span data-ttu-id="e56f1-108">例如:</span><span class="sxs-lookup"><span data-stu-id="e56f1-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="e56f1-109">两个已装箱的对象与通过装箱不可为 null 的类型所创建的对象相同。</span><span class="sxs-lookup"><span data-stu-id="e56f1-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="e56f1-110">并且，与不可以为 null 的装箱类型一样，可将其取消装箱为可为 null 的类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e56f1-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="e56f1-111">备注</span><span class="sxs-lookup"><span data-stu-id="e56f1-111">Remarks</span></span>  
 <span data-ttu-id="e56f1-112">可以为 null 的类型在装箱时的行为可提供两大好处：</span><span class="sxs-lookup"><span data-stu-id="e56f1-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="e56f1-113">可以为 null 的对象和其装箱的对应项可进行 null 测试：</span><span class="sxs-lookup"><span data-stu-id="e56f1-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
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
  
2.  <span data-ttu-id="e56f1-114">装箱的可以为 null 的类型完全支持基础类型的功能：</span><span class="sxs-lookup"><span data-stu-id="e56f1-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e56f1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e56f1-115">See Also</span></span>  
 [<span data-ttu-id="e56f1-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e56f1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e56f1-117">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="e56f1-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="e56f1-118">如何：标识可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="e56f1-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
