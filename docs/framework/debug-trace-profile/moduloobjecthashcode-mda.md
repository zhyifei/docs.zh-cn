---
title: moduloObjectHashcode MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b1223839be3747b04810d6b5bd131733c41631f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614381"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="8054c-102">moduloObjectHashcode MDA</span><span class="sxs-lookup"><span data-stu-id="8054c-102">moduloObjectHashcode MDA</span></span>
<span data-ttu-id="8054c-103">`moduloObjectHashcode` 托管调试助手 (MDA) 更改 <xref:System.Object> 类的行为，以便对 <xref:System.Object.GetHashCode%2A> 方法返回的哈希代码执行取模运算。</span><span class="sxs-lookup"><span data-stu-id="8054c-103">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="8054c-104">此 MDA 的模数默认为 1，这将导致 <xref:System.Object.GetHashCode%2A> 对所有对象都返回 0。</span><span class="sxs-lookup"><span data-stu-id="8054c-104">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8054c-105">症状</span><span class="sxs-lookup"><span data-stu-id="8054c-105">Symptoms</span></span>  
 <span data-ttu-id="8054c-106">在迁移到公共语言运行时 (CLR) 的新版本后，程序将不再正确执行：</span><span class="sxs-lookup"><span data-stu-id="8054c-106">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
- <span data-ttu-id="8054c-107">程序从 <xref:System.Collections.Hashtable> 获得错误的对象。</span><span class="sxs-lookup"><span data-stu-id="8054c-107">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
- <span data-ttu-id="8054c-108"><xref:System.Collections.Hashtable> 中的枚举顺序发生了一项变化，导致程序中断。</span><span class="sxs-lookup"><span data-stu-id="8054c-108">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
- <span data-ttu-id="8054c-109">以前相等的两个对象不再相等。</span><span class="sxs-lookup"><span data-stu-id="8054c-109">Two objects that used to be equal are no longer equal.</span></span>  
  
- <span data-ttu-id="8054c-110">以前不相等的两个对象现在相等。</span><span class="sxs-lookup"><span data-stu-id="8054c-110">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8054c-111">原因</span><span class="sxs-lookup"><span data-stu-id="8054c-111">Cause</span></span>  
 <span data-ttu-id="8054c-112">由于在 <xref:System.Collections.Hashtable> 中的键的类上，<xref:System.Object.Equals%2A> 方法实现通过比较 <xref:System.Object.GetHashCode%2A> 方法调用的结果测试对象是否相等，因此程序可能从 <xref:System.Collections.Hashtable> 中得到错误的对象。</span><span class="sxs-lookup"><span data-stu-id="8054c-112">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="8054c-113">不应该使用哈希代码测试对象是否相等，因为即使两个对象各自的字段具有不同的值，它们也可能具有相同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="8054c-113">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="8054c-114">虽然在实践中很罕见，但的确可能会发生这些哈希代码冲突。</span><span class="sxs-lookup"><span data-stu-id="8054c-114">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="8054c-115">这对 <xref:System.Collections.Hashtable> 查找的影响是两个不相等的键似乎相等，并从 <xref:System.Collections.Hashtable> 返回错误的对象。</span><span class="sxs-lookup"><span data-stu-id="8054c-115">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="8054c-116">出于性能的考虑，<xref:System.Object.GetHashCode%2A> 的实现在运行时的两个版本之间可能改变，因此在一个版本中可能不会出现的冲突可能会在随后的版本中出现。</span><span class="sxs-lookup"><span data-stu-id="8054c-116">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="8054c-117">启用此 MDA 测试代码在哈希代码冲突时是否有 bug。</span><span class="sxs-lookup"><span data-stu-id="8054c-117">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="8054c-118">启用后，此 MDA 将导致 <xref:System.Object.GetHashCode%2A> 方法返回 0，造成所有哈希代码冲突。</span><span class="sxs-lookup"><span data-stu-id="8054c-118">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="8054c-119">启用此 MDA 对程序的唯一影响是程序将会运行得更慢。</span><span class="sxs-lookup"><span data-stu-id="8054c-119">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="8054c-120">如果用于计算键的哈希代码的算法改变，则 <xref:System.Collections.Hashtable> 中的枚举顺序可能随运行时版本而改变。</span><span class="sxs-lookup"><span data-stu-id="8054c-120">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="8054c-121">要测试程序是否依赖键的枚举顺序或哈希表的值，可启用此 MDA。</span><span class="sxs-lookup"><span data-stu-id="8054c-121">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8054c-122">解决方法</span><span class="sxs-lookup"><span data-stu-id="8054c-122">Resolution</span></span>  
 <span data-ttu-id="8054c-123">从不使用哈希代码替换对象标识。</span><span class="sxs-lookup"><span data-stu-id="8054c-123">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="8054c-124">实现 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 方法的重写，以便不比较哈希代码。</span><span class="sxs-lookup"><span data-stu-id="8054c-124">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="8054c-125">不要创建依赖哈希表中的键或值的枚举顺序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="8054c-125">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8054c-126">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="8054c-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="8054c-127">启用了此 MDA 时，应用程序的运行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="8054c-127">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="8054c-128">此 MDA 只取得原本应该返回的哈希代码，改为返回除以某个模数之后得到的余数。</span><span class="sxs-lookup"><span data-stu-id="8054c-128">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8054c-129">Output</span><span class="sxs-lookup"><span data-stu-id="8054c-129">Output</span></span>  
 <span data-ttu-id="8054c-130">此 MDA 没有输出。</span><span class="sxs-lookup"><span data-stu-id="8054c-130">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8054c-131">配置</span><span class="sxs-lookup"><span data-stu-id="8054c-131">Configuration</span></span>  
 <span data-ttu-id="8054c-132">`modulus` 属性指定用于哈希代码的模数。</span><span class="sxs-lookup"><span data-stu-id="8054c-132">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="8054c-133">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="8054c-133">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8054c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8054c-134">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8054c-135">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="8054c-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
