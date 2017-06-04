---
title: "Enhancing Debugging with the Debugger Display Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "debugger, display attributes"
  - "DebuggerTypeProxyAttribute attribute"
  - "debugging [.NET Framework], debugger display attributes"
  - "DebuggerDisplayAttribute attribute"
  - "display attributes for debugger"
  - "DebuggerBrowsableAttribute attribute"
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Enhancing Debugging with the Debugger Display Attributes
调试器显示特性允许类型的开发人员（他们指定并且最理解该类型的运行时行为）同时指定该类型显示在调试器中时的外观。  此外，用户无需知道源代码即可在程序集级别应用提供 `Target` 属性的调试器显示特性。  <xref:System.Diagnostics.DebuggerDisplayAttribute> 特性控制如何在调试器变量窗口中显示类型或成员。  <xref:System.Diagnostics.DebuggerBrowsableAttribute> 特性确定是否以及如何在调试器变量窗口中显示某个字段或属性。  <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 特性指定某个类型的替代类型或代理，并更改在调试器窗口中显示该类型的方式。  在查看具有代理或替代类型的变量时，该代理在调试器显示窗口中代表原始类型。调试器变量窗口仅显示代理类型的公共成员。  不会显示私有成员。  
  
## 使用 DebuggerDisplayAttribute  
 <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> 构造函数具有单个参数：要在类型实例的值列中显示的字符串。  此字符串可以包含大括号（{ 和 }）。  大括号对中的文本按表达式进行求值。  例如，当选择加号 \(\+\) 展开 `MyHashtable` 的实例的调试器显示时，下面的 C\# 代码导致“Count \= 4”被显示出来。  
  
```  
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```  
  
 应用于表达式中引用的属性的特性未被处理。  对于 C\# 编译器，允许使用常规表达式，这些表达式只能对目标类型的当前实例的 this 引用进行隐式访问。  该表达式是受限制的，不存在对别名、局部变量或指针的访问。  在 C\# 代码中，可以在大括号之间使用常规表达式，它们只能对目标类型的当前实例的 `this` 指针进行隐式访问。  
  
 例如，如果 C\# 对象重写了 `ToString()`，则调试器将调用该重写，并显示其结果而不是显示标准的 `{<typeName>}.`。因此，如果重写了 `ToString()`，则不需要使用 <xref:System.Diagnostics.DebuggerDisplayAttribute>。  在同时使用这两者时，<xref:System.Diagnostics.DebuggerDisplayAttribute> 特性将优先于 `ToString()` 重写。  
  
## 使用 DebuggerBrowsableAttribute  
 将 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 应用于某个字段或属性，以指定如何在调试器窗口中显示该字段或属性。  此特性的构造函数采用 <xref:System.Diagnostics.DebuggerBrowsableState> 枚举值之一，该值指定下列状态之一：  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> 指示数据窗口中不显示该成员。例如，将此值用于某字段的 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 将从层次结构中移除该字段；当您通过单击类型实例的加号 \(\+\) 来展开封闭类型时，不会显示该字段。  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> 指示将显示成员但默认情况下不展开。这是默认行为。  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> 指示不显示该成员自身，但是如果它是数组或集合，则显示其构成对象。  
  
> [!NOTE]
>  .NET Framework 2.0 版中的 Visual Basic 不支持 <xref:System.Diagnostics.DebuggerBrowsableAttribute>。  
  
 下面的代码示例演示如何使用 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 阻止它后面的属性出现在类的调试窗口中。  
  
```  
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## 使用 DebuggerTypeProxy  
 在需要显著或根本性地更改类型的调试视图但是不更改类型自身时，应使用 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 特性。  <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 特性用于指定类型的显示代理，允许开发人员定制类型的视图。此特性与 <xref:System.Diagnostics.DebuggerDisplayAttribute> 类似，可以在程序集级别使用，在这种情况下，<xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> 属性指定将为其使用代理的类型。  建议的用法是此特性指定一个私有嵌套类型，它出现在该特性所应用到的类型中。显示类型时，支持类型查看器的表达式计算器将对此特性进行检查。  如果找到该特性，表达式计算器就会替换应用该特性的类型的显示代理类型。  
  
 如果存在 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>，调试器变量窗口将仅显示代理类型的公共成员，  不会显示私有成员。  特性增强的视图不会更改数据窗口的行为。  
  
 为了避免不必要的性能损失，显示代理的特性将在展开对象（可通过用户在数据窗口中单击类型旁的加号 \(\+\)，或通过应用 <xref:System.Diagnostics.DebuggerBrowsableAttribute> 特性）之后处理。  因此，建议不要将任何特性应用于显示类型。  特性可以并且应该在显示类型的代码体中应用。  
  
 下面的代码示例演示如何使用 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 指定将用作调试器显示代理的类型。  
  
```  
  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable : Hashtable  
{  
    private const string TestString =   
        "This should not appear in the debug window.";  
  
    internal class HashtableDebugView  
    {  
        private Hashtable hashtable;  
        public const string TestStringProxy =   
            "This should appear in the debug window.";  
  
        // The constructor for the type proxy class must have a   
        // constructor that takes the target type as a parameter.  
        public HashtableDebugView(Hashtable hashtable)  
        {  
            this.hashtable = hashtable;  
        }  
    }  
}  
```  
  
## 示例  
  
### 说明  
 可以在 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 中查看下面的代码示例以确定应用 <xref:System.Diagnostics.DebuggerDisplayAttribute>、<xref:System.Diagnostics.DebuggerBrowsableAttribute> 和 <xref:System.Diagnostics.DebuggerTypeProxyAttribute> 特性的结果。  
  
### 代码  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## 请参阅  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>   
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>   
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>