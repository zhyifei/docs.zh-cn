---
title: "访问自定义特性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "特性 [.NET Framework], 访问"
  - "自定义特性, 辅助功能"
  - "反射, 自定义特性"
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 访问自定义特性
当特性与程序元素相关联后，可以使用反射来查询它们是否存在以及它们的值。  在 .NET Framework 1.0 和 1.1 版中，是在执行上下文中检查自定义特性。  .NET Framework 2.0 版提供了新的加载上下文（只反射上下文），该上下文可用于检查无法加载执行的代码。  
  
## 只反射上下文  
 加载到只反射上下文中的代码无法执行。  这意味着不能创建自定义特性的实例，因为这将需要执行其构造函数。  若要在只反射上下文中加载和检查自定义特性，请使用 <xref:System.Reflection.CustomAttributeData> 类。  可以通过使用静态 <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> 方法的相应重载获取此类的实例。  请参见[如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。  
  
## 执行上下文  
 用于查询执行上下文中的特性的主要反射方法是 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> 和 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>。  
  
 自定义特性的可访问性根据附加该特性的程序集来进行检查。  这相当于检查附加自定义特性的程序集中，其类型的方法是否可以调用自定义特性的构造函数。  
  
 诸如 <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> 等方法检查类型参数的可见性和可访问性。  只有包含用户定义类型的程序集中的代码才能使用 **GetCustomAttributes** 检索该类型的自定义特性。  
  
 下面的 C\# 示例是典型的自定义特性设计模式。  它说明运行时自定义特性反射模型。  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 如果运行时尝试为附加到 **GetLanguage** 方法的公共自定义特性类型 <xref:System.ComponentModel.DescriptionAttribute> 检索自定义特性，则该运行时将执行下列操作：  
  
1.  运行时检查 **Type.GetCustomAttributes**\(Type *type*\) 的 **DescriptionAttribute** 类型参数是否为公共的，从而是否可见和访问。  
  
2.  运行时检查从 **DescriptionAttribute** 派生的用户定义类型 **MyDescriptionAttribute** 在 **System.Web.DLL** 程序集（它在该程序集中附加到 **GetLanguage**\(\) 方法）内是否可见和可以访问。  
  
3.  运行时检查 **MyDescriptionAttribute** 的构造函数是否在 **System.Web.DLL** 程序集中可见和可以访问。  
  
4.  运行时调用带有自定义特性参数的 **MyDescriptionAttribute** 的构造函数，然后将新对象返回给调用方。  
  
 自定义特性反射模型可能会在定义类型的程序集外泄漏用户定义类型的实例。  这与运行时系统库中返回用户定义类型的实例的成员（例如返回 **RuntimeMethodInfo** 对象数组的 [Type.GetMethods\(\)](frlrfSystemTypeClassGetMethodsTopic)）相同。  为了防止客户端发现关于用户定义的自定义特性类型的信息，请将该类型的成员定义为非公共成员。  
  
 下面的示例说明使用反射访问自定义特性的基本方法。  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## 请参阅  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [查看类型信息](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [反射的安全注意事项](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)