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
ms.openlocfilehash: cc9708b8cca6520932fbf0e1975a05cad5fad485
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115045"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm > 元素
确定公共语言运行时是否按应用程序域计算字符串的哈希代码。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否基于每个应用程序域计算字符串的哈希代码。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|“值”|描述|  
|-----------|-----------------|  
|`0`|公共语言运行时不会为每个应用程序域计算字符串的哈希代码;单个算法用于计算字符串哈希代码。 这是默认设置。|  
|`1`|公共语言运行时基于每个应用程序域计算字符串的哈希代码。 不同应用程序域和不同进程中的相同字符串具有不同的哈希代码。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 默认情况下，<xref:System.StringComparer> 类和 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 方法使用单个哈希算法，该算法可跨应用程序域生成一致的哈希代码。 这等效于将 `<UseRandomizedStringHashAlgorithm>` 元素的 `enabled` 特性设置为 `0`。 这是 .NET Framework 4 中使用的哈希算法。  
  
 <xref:System.StringComparer> 类和 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 方法还可以使用不同的哈希算法来计算每个应用程序域的哈希代码。 因此，相同字符串的哈希代码将在应用程序域之间有所不同。 这是一项可选功能;若要利用它，必须将 `<UseRandomizedStringHashAlgorithm>` 元素的 `enabled` 特性设置为 `1`。  
  
 哈希表中的字符串查找通常为 O （1）操作。 但是，当发生大量冲突时，查找可能会成为 O （n<sup>2</sup>）操作。 你可以使用 `<UseRandomizedStringHashAlgorithm>` 配置元素为每个应用程序域生成随机哈希算法，这反过来会限制潜在冲突的数目，特别是当从中计算哈希代码的键基于的数据输入时那些.  
  
## <a name="example"></a>示例  
 下面的示例定义一个 `DisplayString` 类，该类包含一个私有字符串常量，`s`，其值为 "This is a string"。 它还包括一个 `ShowStringHashCode` 方法，该方法显示字符串值及其哈希代码，以及在其中执行方法的应用程序域的名称。  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 运行该示例时，如果不提供配置文件，它将显示如下所示的输出。 请注意，这两个应用程序域中的字符串的哈希代码是相同的。  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 但是，如果将下面的配置文件添加到示例的目录中，然后运行该示例，则相同字符串的哈希代码将与应用程序域不同。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 如果配置文件存在，则此示例将显示以下输出：  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
