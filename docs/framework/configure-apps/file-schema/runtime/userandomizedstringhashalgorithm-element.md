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
# <a name="userandomizedstringhashalgorithm-element"></a>\<使用随机字符串哈希算法>元素
确定通用语言运行时是否根据每个应用程序域计算字符串的哈希代码。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<使用随机字符串哈希算法>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定字符串的哈希代码是否根据应用程序域计算。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`0`|通用语言运行时不根据每个应用程序域计算字符串的哈希代码;因此，不计算字符串的哈希代码。单个算法用于计算字符串哈希代码。 这是默认值。|  
|`1`|通用语言运行时根据每个应用程序域计算字符串的哈希代码。 不同应用程序域和不同进程中的相同字符串将具有不同的哈希代码。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 默认情况下，<xref:System.StringComparer>类<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>和方法使用单个哈希算法，该算法跨应用程序域生成一致的哈希代码。 这相当于将`enabled``<UseRandomizedStringHashAlgorithm>`元素的属性设置为`0`。 这是 .NET 框架 4 中使用的哈希算法。  
  
 类<xref:System.StringComparer>和方法<xref:System.String.GetHashCode%2A?displayProperty=nameWithType>还可以使用不同的哈希算法，该算法根据每个应用程序域计算哈希代码。 因此，等效字符串的哈希代码将因应用程序域而异。 这是一个选择加入功能;要利用它，必须将`enabled``<UseRandomizedStringHashAlgorithm>`元素的属性设置为`1`。  
  
 哈希表中的字符串查找通常是 O（1） 操作。 但是，当发生大量冲突时，查找可能会成为 O（n<sup>2</sup>） 操作。 您可以使用`<UseRandomizedStringHashAlgorithm>`配置元素生成每个应用程序域的随机哈希算法，从而限制潜在冲突的数量，尤其是当计算哈希代码的键基于用户输入的数据时。  
  
## <a name="example"></a>示例  
 下面的示例定义一个`DisplayString`类，该类包含私有字符串常量`s`，其值为"这是一个字符串"。 它还包括显示字符串值及其哈希代码的 `ShowStringHashCode` 方法以及该方法在其中执行的应用程序域的名称。  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 当您在未提供配置文件的情况下运行该示例时，它会显示类似下面的输出。 请注意，字符串的散列码在两个应用程序域中是相同的。  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 但是，如果将以下配置文件添加到示例目录，然后运行该示例，则同一个字符串的哈希代码将通过应用程序域进行区分。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 存在配置文件时，示例会显示以下输出：  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
