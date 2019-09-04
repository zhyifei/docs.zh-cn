---
title: <UseRandomizedStringHashAlgorithm> 元素
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
ms.openlocfilehash: 49b53dcd4db7e0ac1e9079e763b8ed76c1088e0e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252199"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="10072-102">\<UseRandomizedStringHashAlgorithm > 元素</span><span class="sxs-lookup"><span data-stu-id="10072-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="10072-103">确定公共语言运行时是否按应用程序域计算字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="10072-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="10072-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="10072-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="10072-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="10072-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm>**</span><span class="sxs-lookup"><span data-stu-id="10072-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10072-107">语法</span><span class="sxs-lookup"><span data-stu-id="10072-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10072-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10072-108">Attributes and Elements</span></span>  
 <span data-ttu-id="10072-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10072-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10072-110">特性</span><span class="sxs-lookup"><span data-stu-id="10072-110">Attributes</span></span>  
  
|<span data-ttu-id="10072-111">特性</span><span class="sxs-lookup"><span data-stu-id="10072-111">Attribute</span></span>|<span data-ttu-id="10072-112">描述</span><span class="sxs-lookup"><span data-stu-id="10072-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="10072-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="10072-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="10072-114">指定是否基于每个应用程序域计算字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="10072-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="10072-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="10072-116">值</span><span class="sxs-lookup"><span data-stu-id="10072-116">Value</span></span>|<span data-ttu-id="10072-117">描述</span><span class="sxs-lookup"><span data-stu-id="10072-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="10072-118">公共语言运行时不会为每个应用程序域计算字符串的哈希代码;单个算法用于计算字符串哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="10072-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="10072-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="10072-120">公共语言运行时基于每个应用程序域计算字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="10072-121">不同应用程序域和不同进程中的相同字符串具有不同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10072-122">子元素</span><span class="sxs-lookup"><span data-stu-id="10072-122">Child Elements</span></span>  
 <span data-ttu-id="10072-123">无。</span><span class="sxs-lookup"><span data-stu-id="10072-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10072-124">父元素</span><span class="sxs-lookup"><span data-stu-id="10072-124">Parent Elements</span></span>  
  
|<span data-ttu-id="10072-125">元素</span><span class="sxs-lookup"><span data-stu-id="10072-125">Element</span></span>|<span data-ttu-id="10072-126">描述</span><span class="sxs-lookup"><span data-stu-id="10072-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10072-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="10072-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10072-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="10072-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10072-129">备注</span><span class="sxs-lookup"><span data-stu-id="10072-129">Remarks</span></span>  
 <span data-ttu-id="10072-130">默认情况下， <xref:System.StringComparer>类<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>和方法使用单个哈希算法，该算法可跨应用程序域生成一致的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="10072-131">这等效于将`enabled` `<UseRandomizedStringHashAlgorithm>`元素的特性设置为`0`。</span><span class="sxs-lookup"><span data-stu-id="10072-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="10072-132">这是 .NET Framework 4 中使用的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="10072-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="10072-133"><xref:System.StringComparer> 类<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>和方法也可以使用不同的哈希算法来计算每个应用程序域的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="10072-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="10072-134">因此，相同字符串的哈希代码将在应用程序域之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="10072-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="10072-135">这是一项可选功能;若要利用它，必须将`enabled` `<UseRandomizedStringHashAlgorithm>`元素的属性设置为`1`。</span><span class="sxs-lookup"><span data-stu-id="10072-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="10072-136">哈希表中的字符串查找通常为 O （1）操作。</span><span class="sxs-lookup"><span data-stu-id="10072-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="10072-137">但是，当发生大量冲突时，查找可能会成为 O （n<sup>2</sup>）操作。</span><span class="sxs-lookup"><span data-stu-id="10072-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="10072-138">您可以使用`<UseRandomizedStringHashAlgorithm>` configuration 元素为每个应用程序域生成随机哈希算法，这反过来会限制潜在冲突的数目，特别是当从中计算哈希代码的键基于数据输入时由用户。</span><span class="sxs-lookup"><span data-stu-id="10072-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10072-139">示例</span><span class="sxs-lookup"><span data-stu-id="10072-139">Example</span></span>  
 <span data-ttu-id="10072-140">下面的示例定义了`DisplayString`一个类，该类包含一个私有字符串`s`常量，其值为 "This is a string"。</span><span class="sxs-lookup"><span data-stu-id="10072-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="10072-141">它还包括一个`ShowStringHashCode`方法，该方法显示字符串值及其哈希代码，以及方法在其中执行的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="10072-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="10072-142">运行该示例时，如果不提供配置文件，它将显示如下所示的输出。</span><span class="sxs-lookup"><span data-stu-id="10072-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="10072-143">请注意，这两个应用程序域中的字符串的哈希代码是相同的。</span><span class="sxs-lookup"><span data-stu-id="10072-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="10072-144">但是，如果将下面的配置文件添加到示例的目录中，然后运行该示例，则相同字符串的哈希代码将与应用程序域不同。</span><span class="sxs-lookup"><span data-stu-id="10072-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="10072-145">如果配置文件存在，则此示例将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="10072-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="10072-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="10072-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
