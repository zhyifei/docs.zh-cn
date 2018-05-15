---
title: '&lt;UseRandomizedStringHashAlgorithm&gt;元素'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="03df1-102">&lt;UseRandomizedStringHashAlgorithm&gt;元素</span><span class="sxs-lookup"><span data-stu-id="03df1-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="03df1-103">确定公共语言运行时是否在计算字符串的哈希代码按应用程序域。</span><span class="sxs-lookup"><span data-stu-id="03df1-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="03df1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03df1-104">\<configuration></span></span>  
<span data-ttu-id="03df1-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="03df1-105">\<runtime></span></span>  
<span data-ttu-id="03df1-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="03df1-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03df1-107">语法</span><span class="sxs-lookup"><span data-stu-id="03df1-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03df1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03df1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03df1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03df1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03df1-110">特性</span><span class="sxs-lookup"><span data-stu-id="03df1-110">Attributes</span></span>  
  
|<span data-ttu-id="03df1-111">特性</span><span class="sxs-lookup"><span data-stu-id="03df1-111">Attribute</span></span>|<span data-ttu-id="03df1-112">描述</span><span class="sxs-lookup"><span data-stu-id="03df1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="03df1-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="03df1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="03df1-114">指定是否在计算字符串的哈希代码按应用程序域。</span><span class="sxs-lookup"><span data-stu-id="03df1-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="03df1-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="03df1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="03df1-116">值</span><span class="sxs-lookup"><span data-stu-id="03df1-116">Value</span></span>|<span data-ttu-id="03df1-117">描述</span><span class="sxs-lookup"><span data-stu-id="03df1-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="03df1-118">公共语言运行时不会计算字符串的哈希代码上每个应用程序域;单一算法用于计算字符串哈希代码。</span><span class="sxs-lookup"><span data-stu-id="03df1-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="03df1-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="03df1-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="03df1-120">公共语言运行时计算字符串的哈希代码上每个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="03df1-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="03df1-121">在不同的应用程序域，不同的进程中的相同字符串将具有不同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="03df1-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03df1-122">子元素</span><span class="sxs-lookup"><span data-stu-id="03df1-122">Child Elements</span></span>  
 <span data-ttu-id="03df1-123">无。</span><span class="sxs-lookup"><span data-stu-id="03df1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03df1-124">父元素</span><span class="sxs-lookup"><span data-stu-id="03df1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="03df1-125">元素</span><span class="sxs-lookup"><span data-stu-id="03df1-125">Element</span></span>|<span data-ttu-id="03df1-126">描述</span><span class="sxs-lookup"><span data-stu-id="03df1-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03df1-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="03df1-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="03df1-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="03df1-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03df1-129">备注</span><span class="sxs-lookup"><span data-stu-id="03df1-129">Remarks</span></span>  
 <span data-ttu-id="03df1-130">默认情况下，<xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法使用单一的哈希算法跨应用程序域中生成的一致的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="03df1-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="03df1-131">这相当于设置`enabled`属性`<UseRandomizedStringHashAlgorithm>`元素`0`。</span><span class="sxs-lookup"><span data-stu-id="03df1-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="03df1-132">这是在中使用的哈希算法[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="03df1-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="03df1-133"><xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法还可以使用不同的哈希算法在计算哈希代码斐波那按应用程序域。</span><span class="sxs-lookup"><span data-stu-id="03df1-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="03df1-134">因此，跨应用程序域不同的等效字符串哈希代码。</span><span class="sxs-lookup"><span data-stu-id="03df1-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="03df1-135">这是一项可以选择使用的功能;若要充分利用它，必须设置`enabled`属性`<UseRandomizedStringHashAlgorithm>`元素`1`。</span><span class="sxs-lookup"><span data-stu-id="03df1-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="03df1-136">哈希表中的字符串查找通常是 o （1） 运算。</span><span class="sxs-lookup"><span data-stu-id="03df1-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="03df1-137">但是，大量的冲突发生时，查找可成为 O (n<sup>2</sup>) 操作。</span><span class="sxs-lookup"><span data-stu-id="03df1-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="03df1-138">你可以使用`<UseRandomizedStringHashAlgorithm>`配置元素以生成每个应用程序域，反过来限制的潜在冲突数，尤其是在从其计算哈希代码的键根据数据输入时随机哈希算法由用户。</span><span class="sxs-lookup"><span data-stu-id="03df1-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03df1-139">示例</span><span class="sxs-lookup"><span data-stu-id="03df1-139">Example</span></span>  
 <span data-ttu-id="03df1-140">下面的示例定义`DisplayString`类，包含私有字符串常量， `s`，其值是"这是一个字符串。"</span><span class="sxs-lookup"><span data-stu-id="03df1-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="03df1-141">它还包括`ShowStringHashCode`方法，用于显示的字符串值和哈希代码以及在其中执行方法的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="03df1-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="03df1-142">未提供配置文件运行的示例，它会显示类似于下面的输出。</span><span class="sxs-lookup"><span data-stu-id="03df1-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="03df1-143">请注意，字符串的哈希代码相同的两个应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="03df1-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="03df1-144">但是，如果将下面的配置文件添加到示例的目录并运行示例时，相同的字符串的哈希代码不同由应用程序域。</span><span class="sxs-lookup"><span data-stu-id="03df1-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="03df1-145">当存在配置文件时，该示例将显示下面的输出：</span><span class="sxs-lookup"><span data-stu-id="03df1-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="03df1-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="03df1-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
