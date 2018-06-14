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
ms.locfileid: "32746080"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a>&lt;UseRandomizedStringHashAlgorithm&gt;元素
确定公共语言运行时是否在计算字符串的哈希代码按应用程序域。  
  
 \<configuration>  
\<运行时 >  
\<UseRandomizedStringHashAlgorithm >  
  
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
|`enabled`|必需的特性。<br /><br /> 指定是否在计算字符串的哈希代码按应用程序域。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`0`|公共语言运行时不会计算字符串的哈希代码上每个应用程序域;单一算法用于计算字符串哈希代码。 这是默认设置。|  
|`1`|公共语言运行时计算字符串的哈希代码上每个应用程序域。 在不同的应用程序域，不同的进程中的相同字符串将具有不同的哈希代码。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 默认情况下，<xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法使用单一的哈希算法跨应用程序域中生成的一致的哈希代码。 这相当于设置`enabled`属性`<UseRandomizedStringHashAlgorithm>`元素`0`。 这是在中使用的哈希算法[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。  
  
 <xref:System.StringComparer>类和<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>方法还可以使用不同的哈希算法在计算哈希代码斐波那按应用程序域。 因此，跨应用程序域不同的等效字符串哈希代码。 这是一项可以选择使用的功能;若要充分利用它，必须设置`enabled`属性`<UseRandomizedStringHashAlgorithm>`元素`1`。  
  
 哈希表中的字符串查找通常是 o （1） 运算。 但是，大量的冲突发生时，查找可成为 O (n<sup>2</sup>) 操作。 你可以使用`<UseRandomizedStringHashAlgorithm>`配置元素以生成每个应用程序域，反过来限制的潜在冲突数，尤其是在从其计算哈希代码的键根据数据输入时随机哈希算法由用户。  
  
## <a name="example"></a>示例  
 下面的示例定义`DisplayString`类，包含私有字符串常量， `s`，其值是"这是一个字符串。" 它还包括`ShowStringHashCode`方法，用于显示的字符串值和哈希代码以及在其中执行方法的应用程序域的名称。  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 未提供配置文件运行的示例，它会显示类似于下面的输出。 请注意，字符串的哈希代码相同的两个应用程序域中。  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 但是，如果将下面的配置文件添加到示例的目录并运行示例时，相同的字符串的哈希代码不同由应用程序域。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 当存在配置文件时，该示例将显示下面的输出：  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
