---
title: "执行不区分区域性的大小写更改"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="71fe0-102">执行不区分区域性的大小写更改</span><span class="sxs-lookup"><span data-stu-id="71fe0-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="71fe0-103"><xref:System.String.ToUpper%2A?displayProperty=nameWithType>， <xref:System.String.ToLower%2A?displayProperty=nameWithType>， <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>，和<xref:System.Char.ToLower%2A?displayProperty=nameWithType>方法提供不接受任何参数的重载。</span><span class="sxs-lookup"><span data-stu-id="71fe0-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="71fe0-104">默认情况下，这些不带参数的重载执行基于值的大小写更改<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="71fe0-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="71fe0-105">这将生成可能会因区域性的区分大小写结果。</span><span class="sxs-lookup"><span data-stu-id="71fe0-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="71fe0-106">若要清除你是否想区分区域性的或不区分区域性的大小写更改，应使用要求你显式指定这些方法的重载`culture`参数。</span><span class="sxs-lookup"><span data-stu-id="71fe0-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="71fe0-107">对于区分区域性的大小写更改，指定`CultureInfo.CurrentCulture`为`culture`参数。</span><span class="sxs-lookup"><span data-stu-id="71fe0-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="71fe0-108">对于不区分区域性的大小写更改，指定`CultureInfo.InvariantCulture`为`culture`参数。</span><span class="sxs-lookup"><span data-stu-id="71fe0-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="71fe0-109">通常情况下，字符串将转换为标准的情况下，以在稍后启用更轻松查找。</span><span class="sxs-lookup"><span data-stu-id="71fe0-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="71fe0-110">如果字符串将用这种方式中，你应指定`CultureInfo.InvariantCulture`为`culture`参数，因为值<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>更改这种情况的时间和查找发生的时间之间可能发生更改。</span><span class="sxs-lookup"><span data-stu-id="71fe0-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="71fe0-111">如果安全决策基于大小写更改操作，则操作应该区分区域性，以确保结果不受的值`CultureInfo.CurrentCulture`。</span><span class="sxs-lookup"><span data-stu-id="71fe0-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="71fe0-112">请参阅的"字符串比较，使用当前区域性"部分[使用字符串的最佳实践](../../../docs/standard/base-types/best-practices-strings.md)文章的一个示例，演示如何区分区域性的字符串操作变得不一致的结果。</span><span class="sxs-lookup"><span data-stu-id="71fe0-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="71fe0-113">使用 String.ToUpper 和 String.ToLower 方法</span><span class="sxs-lookup"><span data-stu-id="71fe0-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="71fe0-114">有关代码的清楚起见，建议你始终使用重载`String.ToUpper`和`String.ToLower`允许你指定的方法`culture`参数显式。</span><span class="sxs-lookup"><span data-stu-id="71fe0-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="71fe0-115">例如，下面的代码执行了标识符查找。</span><span class="sxs-lookup"><span data-stu-id="71fe0-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="71fe0-116">`key.ToLower`操作是区分区域性的默认情况下，但此行为并不清楚从阅读代码。</span><span class="sxs-lookup"><span data-stu-id="71fe0-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="71fe0-117">示例</span><span class="sxs-lookup"><span data-stu-id="71fe0-117">Example</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 <span data-ttu-id="71fe0-118">如果你想`key.ToLower`操作是不区分区域性的应更改前面的示例中，如下所示，若要显式使用`CultureInfo.InvariantCulture`时更改大小写。</span><span class="sxs-lookup"><span data-stu-id="71fe0-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="71fe0-119">使用 Char.ToUpper 和 Char.ToLower 方法</span><span class="sxs-lookup"><span data-stu-id="71fe0-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="71fe0-120">尽管`Char.ToUpper`和`Char.ToLower`方法具有相同的特征作为`String.ToUpper`和`String.ToLower`方法，受影响的唯一区域性为土耳其语 （土耳其） 和阿塞拜疆语 （拉丁，阿塞拜疆）。</span><span class="sxs-lookup"><span data-stu-id="71fe0-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="71fe0-121">这些是使用单字符大小写差异的仅有两个区域性。</span><span class="sxs-lookup"><span data-stu-id="71fe0-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="71fe0-122">有关此唯一大小写映射的详细信息，请参阅 <xref:System.String> 类主题中的“大小写”部分。</span><span class="sxs-lookup"><span data-stu-id="71fe0-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="71fe0-123">有关代码的清楚起见并确保一致的结果，建议你始终使用允许你显式指定这些方法的重载`culture`参数。</span><span class="sxs-lookup"><span data-stu-id="71fe0-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71fe0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71fe0-124">See Also</span></span>  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="71fe0-125">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="71fe0-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
