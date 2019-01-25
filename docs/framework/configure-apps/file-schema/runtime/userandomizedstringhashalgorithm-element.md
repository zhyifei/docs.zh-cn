---
title: '&lt;Userandomizedstringhashalgorithm，那么&gt;元素'
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
ms.openlocfilehash: 3bb4286ea6055d2df9111b2222b137f2668bfdfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681035"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="d144b-102">&lt;Userandomizedstringhashalgorithm，那么&gt;元素</span><span class="sxs-lookup"><span data-stu-id="d144b-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="d144b-103">确定公共语言运行时是否在计算字符串的哈希代码每个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d144b-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="d144b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d144b-104">\<configuration></span></span>  
<span data-ttu-id="d144b-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="d144b-105">\<runtime></span></span>  
<span data-ttu-id="d144b-106">\<UseRandomizedStringHashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="d144b-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d144b-107">语法</span><span class="sxs-lookup"><span data-stu-id="d144b-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d144b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d144b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d144b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d144b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d144b-110">特性</span><span class="sxs-lookup"><span data-stu-id="d144b-110">Attributes</span></span>  
  
|<span data-ttu-id="d144b-111">特性</span><span class="sxs-lookup"><span data-stu-id="d144b-111">Attribute</span></span>|<span data-ttu-id="d144b-112">描述</span><span class="sxs-lookup"><span data-stu-id="d144b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d144b-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d144b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d144b-114">指定字符串的哈希代码计算每个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d144b-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d144b-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d144b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d144b-116">值</span><span class="sxs-lookup"><span data-stu-id="d144b-116">Value</span></span>|<span data-ttu-id="d144b-117">描述</span><span class="sxs-lookup"><span data-stu-id="d144b-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="d144b-118">公共语言运行时不会计算字符串的哈希代码对每个应用程序域;使用单个算法来计算字符串哈希代码。</span><span class="sxs-lookup"><span data-stu-id="d144b-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="d144b-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d144b-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="d144b-120">公共语言运行时计算字符串的哈希代码对每个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d144b-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="d144b-121">在不同应用程序域和不同进程中的相同字符串将具有不同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="d144b-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d144b-122">子元素</span><span class="sxs-lookup"><span data-stu-id="d144b-122">Child Elements</span></span>  
 <span data-ttu-id="d144b-123">无。</span><span class="sxs-lookup"><span data-stu-id="d144b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d144b-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d144b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d144b-125">元素</span><span class="sxs-lookup"><span data-stu-id="d144b-125">Element</span></span>|<span data-ttu-id="d144b-126">描述</span><span class="sxs-lookup"><span data-stu-id="d144b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d144b-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d144b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d144b-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="d144b-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d144b-129">备注</span><span class="sxs-lookup"><span data-stu-id="d144b-129">Remarks</span></span>  
 <span data-ttu-id="d144b-130">默认情况下<xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法使用跨应用程序域生成一致的哈希代码的单个哈希算法。</span><span class="sxs-lookup"><span data-stu-id="d144b-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="d144b-131">这相当于设置`enabled`的属性`<UseRandomizedStringHashAlgorithm>`元素`0`。</span><span class="sxs-lookup"><span data-stu-id="d144b-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="d144b-132">这是在中使用的哈希算法[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d144b-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="d144b-133"><xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法还可以使用不同的哈希算法计算哈希代码对每个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d144b-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="d144b-134">因此，等效的字符串的哈希代码将不同跨应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d144b-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="d144b-135">这是一项选择加入的功能;若要充分利用它，必须设置`enabled`的属性`<UseRandomizedStringHashAlgorithm>`元素`1`。</span><span class="sxs-lookup"><span data-stu-id="d144b-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="d144b-136">哈希表中的字符串查找通常是 o （1） 的操作。</span><span class="sxs-lookup"><span data-stu-id="d144b-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="d144b-137">但是，大量冲突发生时，查找会变为 O (n<sup>2</sup>) 操作。</span><span class="sxs-lookup"><span data-stu-id="d144b-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="d144b-138">可以使用`<UseRandomizedStringHashAlgorithm>`要生成随机的哈希算法，每个应用程序域，从而限制潜在冲突数量，尤其是在从其计算哈希代码的密钥根据数据输入时配置元素由用户。</span><span class="sxs-lookup"><span data-stu-id="d144b-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d144b-139">示例</span><span class="sxs-lookup"><span data-stu-id="d144b-139">Example</span></span>  
 <span data-ttu-id="d144b-140">下面的示例定义`DisplayString`类，其中包含私有字符串常量， `s`，其值是"这是一个字符串"。</span><span class="sxs-lookup"><span data-stu-id="d144b-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="d144b-141">它还包括`ShowStringHashCode`显示的字符串值和其哈希代码，以及在其中执行方法的应用程序域的名称的方法。</span><span class="sxs-lookup"><span data-stu-id="d144b-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="d144b-142">不提供配置文件的情况下运行该示例时，它会显示类似于以下的输出。</span><span class="sxs-lookup"><span data-stu-id="d144b-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="d144b-143">请注意，该字符串的哈希代码完全相同的两个应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="d144b-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="d144b-144">但是，如果将下面的配置文件添加到该示例的目录，然后运行该示例相同的字符串的哈希代码将通过应用程序域不同。</span><span class="sxs-lookup"><span data-stu-id="d144b-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d144b-145">当存在配置文件时，该示例将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="d144b-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="d144b-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d144b-146">See also</span></span>
- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
