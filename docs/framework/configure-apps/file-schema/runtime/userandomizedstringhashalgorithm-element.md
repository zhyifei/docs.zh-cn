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
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153772"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="65d4e-102">\<使用随机字符串哈希算法>元素</span><span class="sxs-lookup"><span data-stu-id="65d4e-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="65d4e-103">确定通用语言运行时是否根据每个应用程序域计算字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="65d4e-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="65d4e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="65d4e-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="65d4e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="65d4e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<使用随机字符串哈希算法>**</span><span class="sxs-lookup"><span data-stu-id="65d4e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d4e-107">语法</span><span class="sxs-lookup"><span data-stu-id="65d4e-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65d4e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="65d4e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="65d4e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="65d4e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65d4e-110">属性</span><span class="sxs-lookup"><span data-stu-id="65d4e-110">Attributes</span></span>  
  
|<span data-ttu-id="65d4e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="65d4e-111">Attribute</span></span>|<span data-ttu-id="65d4e-112">说明</span><span class="sxs-lookup"><span data-stu-id="65d4e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="65d4e-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="65d4e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="65d4e-114">指定字符串的哈希代码是否根据应用程序域计算。</span><span class="sxs-lookup"><span data-stu-id="65d4e-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="65d4e-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="65d4e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="65d4e-116">值</span><span class="sxs-lookup"><span data-stu-id="65d4e-116">Value</span></span>|<span data-ttu-id="65d4e-117">说明</span><span class="sxs-lookup"><span data-stu-id="65d4e-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="65d4e-118">通用语言运行时不根据每个应用程序域计算字符串的哈希代码;因此，不计算字符串的哈希代码。单个算法用于计算字符串哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="65d4e-119">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="65d4e-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="65d4e-120">通用语言运行时根据每个应用程序域计算字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="65d4e-121">不同应用程序域和不同进程中的相同字符串将具有不同的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65d4e-122">子元素</span><span class="sxs-lookup"><span data-stu-id="65d4e-122">Child Elements</span></span>  
 <span data-ttu-id="65d4e-123">无。</span><span class="sxs-lookup"><span data-stu-id="65d4e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65d4e-124">父元素</span><span class="sxs-lookup"><span data-stu-id="65d4e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="65d4e-125">元素</span><span class="sxs-lookup"><span data-stu-id="65d4e-125">Element</span></span>|<span data-ttu-id="65d4e-126">说明</span><span class="sxs-lookup"><span data-stu-id="65d4e-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="65d4e-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="65d4e-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="65d4e-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="65d4e-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65d4e-129">备注</span><span class="sxs-lookup"><span data-stu-id="65d4e-129">Remarks</span></span>  
 <span data-ttu-id="65d4e-130">默认情况下，<xref:System.StringComparer>类<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>和方法使用单个哈希算法，该算法跨应用程序域生成一致的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="65d4e-131">这相当于将`enabled``<UseRandomizedStringHashAlgorithm>`元素的属性设置为`0`。</span><span class="sxs-lookup"><span data-stu-id="65d4e-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="65d4e-132">这是 .NET 框架 4 中使用的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="65d4e-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="65d4e-133">类<xref:System.StringComparer>和方法<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>还可以使用不同的哈希算法，该算法根据每个应用程序域计算哈希代码。</span><span class="sxs-lookup"><span data-stu-id="65d4e-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="65d4e-134">因此，等效字符串的哈希代码将因应用程序域而异。</span><span class="sxs-lookup"><span data-stu-id="65d4e-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="65d4e-135">这是一个选择加入功能;要利用它，必须将`enabled``<UseRandomizedStringHashAlgorithm>`元素的属性设置为`1`。</span><span class="sxs-lookup"><span data-stu-id="65d4e-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="65d4e-136">哈希表中的字符串查找通常是 O（1） 操作。</span><span class="sxs-lookup"><span data-stu-id="65d4e-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="65d4e-137">但是，当发生大量冲突时，查找可能会成为 O（n<sup>2</sup>） 操作。</span><span class="sxs-lookup"><span data-stu-id="65d4e-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="65d4e-138">您可以使用`<UseRandomizedStringHashAlgorithm>`配置元素生成每个应用程序域的随机哈希算法，从而限制潜在冲突的数量，尤其是当计算哈希代码的键基于用户输入的数据时。</span><span class="sxs-lookup"><span data-stu-id="65d4e-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65d4e-139">示例</span><span class="sxs-lookup"><span data-stu-id="65d4e-139">Example</span></span>  
 <span data-ttu-id="65d4e-140">下面的示例定义一个`DisplayString`类，该类包含私有字符串常量`s`，其值为"这是一个字符串"。</span><span class="sxs-lookup"><span data-stu-id="65d4e-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="65d4e-141">它还包括显示字符串值及其哈希代码的 `ShowStringHashCode` 方法以及该方法在其中执行的应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="65d4e-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="65d4e-142">当您在未提供配置文件的情况下运行该示例时，它会显示类似下面的输出。</span><span class="sxs-lookup"><span data-stu-id="65d4e-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="65d4e-143">请注意，字符串的散列码在两个应用程序域中是相同的。</span><span class="sxs-lookup"><span data-stu-id="65d4e-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="65d4e-144">但是，如果将以下配置文件添加到示例目录，然后运行该示例，则同一个字符串的哈希代码将通过应用程序域进行区分。</span><span class="sxs-lookup"><span data-stu-id="65d4e-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="65d4e-145">存在配置文件时，示例会显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="65d4e-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="65d4e-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65d4e-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
