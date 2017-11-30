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
# <a name="performing-culture-insensitive-case-changes"></a>执行不区分区域性的大小写更改
<xref:System.String.ToUpper%2A?displayProperty=nameWithType>， <xref:System.String.ToLower%2A?displayProperty=nameWithType>， <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>，和<xref:System.Char.ToLower%2A?displayProperty=nameWithType>方法提供不接受任何参数的重载。 默认情况下，这些不带参数的重载执行基于值的大小写更改<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>。 这将生成可能会因区域性的区分大小写结果。 若要清除你是否想区分区域性的或不区分区域性的大小写更改，应使用要求你显式指定这些方法的重载`culture`参数。 对于区分区域性的大小写更改，指定`CultureInfo.CurrentCulture`为`culture`参数。 对于不区分区域性的大小写更改，指定`CultureInfo.InvariantCulture`为`culture`参数。  
  
 通常情况下，字符串将转换为标准的情况下，以在稍后启用更轻松查找。 如果字符串将用这种方式中，你应指定`CultureInfo.InvariantCulture`为`culture`参数，因为值<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>更改这种情况的时间和查找发生的时间之间可能发生更改。  
  
 如果安全决策基于大小写更改操作，则操作应该区分区域性，以确保结果不受的值`CultureInfo.CurrentCulture`。 请参阅的"字符串比较，使用当前区域性"部分[使用字符串的最佳实践](../../../docs/standard/base-types/best-practices-strings.md)文章的一个示例，演示如何区分区域性的字符串操作变得不一致的结果。  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>使用 String.ToUpper 和 String.ToLower 方法  
 有关代码的清楚起见，建议你始终使用重载`String.ToUpper`和`String.ToLower`允许你指定的方法`culture`参数显式。 例如，下面的代码执行了标识符查找。 `key.ToLower`操作是区分区域性的默认情况下，但此行为并不清楚从阅读代码。  
  
### <a name="example"></a>示例  
  
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
  
 如果你想`key.ToLower`操作是不区分区域性的应更改前面的示例中，如下所示，若要显式使用`CultureInfo.InvariantCulture`时更改大小写。  
  
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
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>使用 Char.ToUpper 和 Char.ToLower 方法  
 尽管`Char.ToUpper`和`Char.ToLower`方法具有相同的特征作为`String.ToUpper`和`String.ToLower`方法，受影响的唯一区域性为土耳其语 （土耳其） 和阿塞拜疆语 （拉丁，阿塞拜疆）。 这些是使用单字符大小写差异的仅有两个区域性。 有关此唯一大小写映射的详细信息，请参阅 <xref:System.String> 类主题中的“大小写”部分。 有关代码的清楚起见并确保一致的结果，建议你始终使用允许你显式指定这些方法的重载`culture`参数。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
