---
title: "如何：将程序集加载到仅反射上下文中 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 为反射加载"
  - "程序集 [.NET Framework], 仅限反射的加载程序上下文"
  - "特性 [.NET Framework], 检索"
  - "反射, 仅限反射的加载程序上下文"
  - "仅限反射的加载程序上下文"
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 如何：将程序集加载到仅反射上下文中
只反射加载上下文使您能够检查为其他平台或 .NET Framework 的其他版本编译的程序集。  加载到此上下文中的代码只能检查，不能执行。  这意味着无法创建对象，因为无法执行构造函数。  因为该代码无法执行，所以不会自动加载依赖项。  如果需要对依赖项进行检查，则必须自行加载。  
  
### 将程序集加载到只反射加载上下文中  
  
1.  使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> 方法重载可加载给定了显示名称的程序集，而使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 方法可加载给定了路径的程序集。  如果该程序集为二进制文件映像，则使用 [ReflectionOnlyLoad\(Byte\<xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> 方法重载。  
  
    > [!NOTE]
    >  您不能使用只反射上下文从非执行上下文中的 .NET Framework 版本加载 mscorlib.dll 版本。  
  
2.  如果该程序集具有依赖项，<xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 方法不会加载这些依赖项。  如果需要对依赖项进行检查，则必须自行加载。  
  
3.  使用程序集的 <xref:System.Reflection.Assembly.ReflectionOnly%2A> 属性确定是否将该程序集加载到了只反射上下文中。  
  
4.  如果向该程序集或程序集中的类型应用了特性，则应通过使用 <xref:System.Reflection.CustomAttributeData> 类检查这些特性，以确保未尝试在只反射上下文中执行代码。  使用 <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> 方法的适当重载可获取表示应用于程序集、成员、模块或参数的特性的 <xref:System.Reflection.CustomAttributeData> 对象。  
  
    > [!NOTE]
    >  应用于该程序集或其内容的特性可能是在该程序集中定义的，也可能是在加载到只反射上下文中的另一个程序集中定义的。  无法事先知道这些特性是在何处定义的。  
  
## 示例  
 下面的代码示例演示如何检查应用于加载到只反射上下文中的程序集的特性。  
  
 该代码示例定义了一个带有两个构造函数和一个属性的自定义特性。  该特性可应用于程序集、在该程序集中声明的类型、该类型的方法以及该方法的参数。  在执行时，该程序集将其本身加载到只反射上下文中，并显示应用到它及它包含的类型和成员的自定义特性的有关信息。  
  
> [!NOTE]
>  为简化该代码示例，该程序集自行完成加载和检查操作。  通常情况下，不要在执行上下文和只反射上下文中加载同一程序集。  
  
 [!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
 [!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
 [!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]  
  
## 请参阅  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 <xref:System.Reflection.Assembly.ReflectionOnly%2A>   
 <xref:System.Reflection.CustomAttributeData>